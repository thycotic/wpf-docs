[title]: # (Session Recording)
[tags]: # (WPF)
[priority]: # (10)

# Session Recording

Session Recording for web sessions is supported in the Web Password Filler. For a web session to be recorded, the Secret (in Secret Server) must have Session Recording enabled in the Security settings.

When you launch a Secret that has Session Recording enabled, or when you navigate to a web page and select a Secret that has Session Recording enabled, the recording begins as soon as the credentials are filled into the login fields (Username/Password, etc.).

Once the session recording starts you should see a notification message pop up at the upper right side of the browser window indicating that recording has begun. On sites that allow it, the logo on the tab will alternate between the site logo and the recording icon.

When recording web sessions, the recording will be limited to the exact match for the domain/subdomain for the URL, which is everything between `http(s)://` and the next `/`. Anything *not* included in the exact URL will not be recorded. For example, if a Secret with session recording has the URL value set to `https://thycotic.company.com/` then only the browser tabs opened for that URL will be recorded. If the login page then redirects to `https://company.com` then the session will no longer be recorded since the subdomain has changed.

Likewise, you might be recording a session in a tab opened to `https://thycotic.company.com` and then open a second tab to `https://delta.company.com`, which happens to use the same domain as the first tab (`company.com`). When the second tab opens it becomes the tab "in focus" and the session recording continues on the second tab. If you wish to keep recording on the original tab, we recommend opening the second tab in an incognito window or in a separate browser session.

If you have session recording enabled for two Secrets that contain the same primary or secondary domain such as `microsoftonline.com` and the same host name (`microsoftonline.com`) AND both secrets are being used, when the second session is selected, WPF will close the first session and tabs associated with the first Secret.

This is expected behavior, implemented to ensure that the only sessions recorded are those associated with Secrets that require session recording. Sites like microsoftonline allow only one login / active credential at a time. If you have session recording enabled for two secrets that do not contain a primary / secondary domain (such as .net, .com, .co) address, both sessions will be recorded independently. For instance red.local.something is not the same as blue.local.something because “something” is neither a primary domain nor secondary domain identifier.

IP Addresses are now treated as an entirely unique address (e.g. 10.0.0.61 is not the same as 10.0.0.51) and will be recorded independently.

## Session Recording Limits

The default maximum recording time for each session (start to end) regardless of how many tabs are open, is two hours. If a user starts session recording on red.thycotic.com, and then opens a tab for blue.thycotic.com, session recording will continue on blue.thycotic.com when it is in focus. By default, session recording will stop after two hours, and both tabs will close. This session recording limit can be extended to a maximum of eight hours by configuring the [Native Messaging Host](../native.md) file.

If you want to capture other sites with different subdomains that launch from the same Secret, you must use RegEx to configure the Secret to include the other URLs.

## RegEx

RegEx is a sequence of patterns specified in Secret Server templates and provided to be specified as __OtherUrls__ during account setup in Web Password Filler (WPF), allowing session recording on redirected websites.

When a user is logged into a website using a secret and session recording is enabled, WPF will record a session for that URL. If a user is redirected to another URL and session recording should continue for the redirected URL, those URLs can be added in the __OtherUrls__ field when the account is added. Currently this field supports only URLs.

>**Note**: That as soon as a URL is accessed for a website and secret with session recording enabled, session recording will capture everything the user does, even if the user changes a password for that secret.

### Using RegEx in WPF

1. To add a new secret via WPF, select a Secret Server template that has the RegEx field.

   ![regex-1](images/regex-1.png "Add Account to Secret Server modal")
1. Click __OK__.
1. In the new Add Account to Secret Server dialog add the required details.

   ![regex-2](images/regex-2.png "Add Account to Secret Server with RegEx template selected")

   In the field __OtherUrls__,  enter any other URL for which session recording should enabled, in the event that the user is redirected to those URLs.  
1. Click __Add__.

### Setup in Secret Server

1. Sign into Secret Server and navigate to __Admin | Secret Templates__.

   ![templates](images/create-secret.png "Templates pages with create new button")
1. Click __Create New__.
1. Name the new secret and click __Create__.

   ![create new page](images/create-secret-2.png "Create new secret template page")
1. On the __Settings__ page, click __Configure Extended Mappings__.

   ![extended map](images/create-secret-3.png "Settings page with configure extended mappings button")
1. On the __Secret Template Extended Mappings__ page click __Add New Mapping__.

   ![config](images/create-secret-4.png "Secret Template Extended Mappings page with drop-down menus")

   1. From the __Extended Mapping to use__ drop-down select __Regex List__.
   1. From the __Regex List Field__ drop-down select __OtherUrls__.
   1. Click __Save__.

The template is now ready to be used in WPF.

If you have session recording enabled for two secrets that contain the same primary or secondary domain (e.g. microsoftonline.com) and the same host name (e.g. microsoftonline.com) AND both secrets are used, WPF will close the first session when the second session is selected, closing the tabs associated with the first secret. This is expected behavior, ensuring that the only sessions recorded are those associated with secrets that require session recording. Sites like _microsoftonline_ only allow one login / active credential at a time.

If you have session recording enabled for two secrets that do not contain a primary / secondary domain (e.g. .net, .com, .co.in) address, both secrets will be recorded independently. For instance red.local.something is not the same as blue.local.something because “something” is neither a primary domain or secondary domain identifier.

IP Addresses are now treated as an entirely unique address  (e.g. 10.0.0.61 is not the same as 10.0.0.51) and will be recorded independently.

>**Note**: WPF records sessions for the account that was used to log into the Windows Admin Center directly. However, WPF **cannot** record RDP sessions logged into after that, because the main browser window still referes to the Windows Admin Center URL, and **not** to the RDP window nested inside the browser page.
