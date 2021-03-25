[title]: # (URL Structural Breakdown)
[tags]: # (URL, domain, structure, breakdown)
[priority]: # (15)

# How WPF Processes URL Components

A Universal Resource Locator (URL) is typically composed of several components as described below.

## Component 1 (required): **Scheme**

The *scheme* identifies the protocol to be used to access the resource on the Internet. It can be HTTP (without SSL) or HTTPS (with SSL).

**WPF treats different schemes as different URLs**

For example `http://company.com` is *not* the same as `https://company.com`. 

## Component 2 (required): **Host**
The *host* identifies where the desired resource is stored, for example `www.company.com`. Host names are used to map to an IP address, but not in a one-to-one relationship. `www.hostone.com` and `www.hosttwo.com` could both point to the same IP address.

The *host* component can be further broken down into subcomponents as shown below:

### Subcomponent 2a (optional): **Subdomain** (including www)

A subdomain identifier could really be any value. For example in `www.company.com` and `eval.company.com`, `www` and `eval` are subdomains of the domain, `company.com`. WPF treats subdomains as different URLS when providing Secrets. Note that when `www` appears in its usual position immediately after `http://` or `https://`, WPF ignores it. **However**, because single sign-on works for a domain regardless of the subdomain, session recording treats all URLs with a given *host* name as the same. 

### Subcomponent 2b (optional): **Domain Extension** (.com, .org, etc.)

A Domain Extension is optional when using internal mappings like `localhost`, which knows how to resolve to the IPv4 loopback address 127.0.0.1.

#### Subcomponent 2b1 (optional): Domain Extensions can also include **Country Codes**

**WPF takes the domain extensions into account when providing secrets.**

For example, `com.de` is a .com extension for Germany, and `company.com` is *not* the same as `company.com.de`

## Component 3 (optional): **Port Number**

Host names can be followed by a port number.
Well-known port numbers for a service are normally omitted from the URL. For example port 80 for http, port 443 for https. Most servers use the well-known port numbers for HTTP and HTTPS , so most HTTP URLs omit the port number.

**WPF takes port numbers into account for a given URL when providing secrets.**

`company.com` and `company.com:8080` are *not* seen as the same site.

## Component 4 (optional): **Path**

The path identifies the specific resource on the host that the web client wants to access, such as `/software/htp/cics/index.html`. The path is optional because servers can be configured to point to specified paths. For instance `https://company.com` can be defined to point to `10.20.20.20/somepath/index.html`.

### Subcomponent 4a (optional): **Section Identifier**

A hash sign (#) in a URL is known as a *fragment*. Historically, URL fragments have been used to automatically set the browser’s scroll position to a predefined location on the web page. In that sense, if a URL refers to a document, then the fragment refers to a specific subsection of that document. The browser interprets `www.company.com/fruits.html#apple` and `www.company.com/fruits.html#orange` as different sections of the same page. It is important to note that hash value changes are *not* the same as page or location changes. 

**Currently, WPF and the Native Messaging Host decide whether to provide a Secret at a "page" level, based on the path only and *not* on a section identifier.**

## Component 5 (optional): **Query string**

If a query string is used, it follows the path component, and provides a string of information that the resource can use for some purpose (for example, as parameters for a search or as data to be processed). The query string is usually a string of name and value pairs. 
Name and value pairs are separated from each other by an ampersand (&);

**WPF completely ignores query strings.**

## A web domain is not the same thing as a website

The domain is read from **right** to left.

For example when examining `www.company.com`:

1. **.com** is the top-level domain
1. **company.com** is the domain
1. **www.company.com** is a subdomain

## How does WPF find the user name element?

WPF finds the *user name* element based on the best match from common attributes including those listed below. If the element contains an attribute of “search," it typically means the field is used to search for a user, and is not an actual user name field, so WPF ignores it.

* account 
* account id 
* accounted 
* apple id 
* domain 
* email 
* email address 
* email_address 
* login
* onlineid 
* tel 
* telephone 
* user 
* user id 
* user name 
* user_name 
* userid 
* username 
* usr (soon) 

If WPF finds a *password* element in a form, it looks  for the closest element to a password element that contains any of the common attributes listed above. 

## Why is the password field and/or user name field being populated?

<!---Neil reworking next paragraph, might go in to Release Notes--->
When a site uses section identifiers (see Subcomponent 4A above) and or hides and shows elements or forms based on some action AND the secret was already selected, WPF has already populated the fields before they were visible. We are working on correcting this behavior so that only visible elements are populated however we risk breaking cases where there are multiple steps to logging in (provide user name, then the password element becomes visible)

