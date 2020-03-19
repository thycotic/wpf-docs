[title]: # (Investigation)
[tags]: # (WPF)
[priority]: # (81)
# Investigating WPF Issues

When investigating issues with the Web Password Filler (WPF) the following questions should help narrow down the issue or provided needed information to troubleshoot.

## Confirm WPF Version

Confirm that the issue is with the new Web Password Filler that was first released in Dec 2019 and in conjunction with Secret Serverv10.7.59.

Problems with other browser extensions/plugins (e.g. Login Assist, Clipboard Utility etc.) should not be deemed as WPF issues.

## Identify the Browser

What browser is the issue occurring on?

* We currently support: Chrome, Firefox, Edge (Chromium) and Opera.

  General Chromium should work as well, but it is not officially supported.
* Does the issue only occur on one browser? Or does it reproduce for multiple/all browsers?
* If it only reproduces on one browser, which one?

## Site Information

Is the issue occurring on a Specific site? Or all sites?

* If the issue only happens on one site, what is the URL for that site?

  For example, if the issue only occurs on Facebook, then we need the URL for the Facebook page that the browser is on when it fails.

* For issues of the WPF login failing, if you change the web page you are on when you try to login does it still occur?

* We will always want to know what **URL** you are on when an issue occurs, since some web pages might be trying to interfere with WPF.

## Access to Site

How are you accessing the site to use WPF?

There are typically two ways to access a page to use WPF:

1. Logging into the Secret Server Web UI and clicking the Web Launcher option to open a new tab

2. Opening a web browser and navigating to a page manually (using a bookmark or typing/searching for the URL). Once on the page we'll fill the credentials or provide options in a pop-up.

## What version of WPF are you encountering the issue on?

We don't list the version number in WPF directly, so you will need to go to the Extensions/Add-on page to get the version number. The location to get this value is roughly, but each browser does it slightly differently.

Basic steps to get this value are:

1. Go to the Settings menu in the browser. This it typically in the top right corner (and looks like a hamburger menu)
1. In the drop-down list select:

   * **Chrome** – More tools \> Extensions
   * **Firefox** – Add-ons
   * **Edge (Chromium)** – Extensions
   * **Opera** – Extensions (in the left-hand menu).
1. The version number will be listed:

   * **Chrome** – At the top of the extension, in-line with the name.
   * **Firefox** – Click on the add-on to get the details and there will be a "Version" field.
   * **Edge (Chromium)** – At the top of the extension, in-line with the name.
   * **Opera** – At the top of the extension directly under the extension name.

## Action to be Performed

What type of action are you trying to perform?

There are a few basic action types that a user might be trying to take.
They can include:

1. Login to WPF
1. Launching a Secret for a web page (from Secret Server or by going to the page manually)

This includes filling credentials for a site

1. Trying to add a new Secret for a site.
1. Trying to update a password for an existing Secret.

## Templates Used

What Secret template are they using?

The Web Password Filler is primarily designed to work with Secrets that use the Web Password template but can work for Secrets that use other templates.

In order to work with other Secret templates those templates need to have a URL field.

1. WPF uses this field to match the URL from the site back with the URL in the Secret.

   >**Note**: The URL field needs to be listed as "Searchable" in the Edit Templates screen in Secret Server.
