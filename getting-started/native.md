[title]: # (Native Message Handling)
[tags]: # (WPF)
[priority]: # (15)
# Thycotic Web Password Filler Native Messaging Handler

Native messaging enables a browser extension to exchange messages with a native application that is installed on the user's computer. The Thycotic Native Messaging Handler serves the Thycotic Web Password Filler settings and configuration options without needing additional accesses over the web and
allows an administrator to establish the default settings for Thycotic Web Password Filler. The Thycotic Native message handler consists of a single executable and a configuration file. Each time a user’s browser is launched, the Thycotic Native Message Handler silently communicates with the Thycotic Web
Password Launcher to establish the default values for configuration and Settings. Additionally, before the Thycotic Web Password Filler attempts to retrieve any secrets associated with a URL, an exclusion list can be added, instructing the Thycotic Web Password Filler to not retrieve, populate or save secrets unless a specific page is active.

## Does the Web Password Filler Require the Thycotic Native Message Handler?

No, the Thycotic Web Password Filler can still run normally without the Thycotic Native Message Handler, however the end user will be required to supply the Secret Server URL and modify any settings to meet their needs.

## Installing the Thycotic Native Message Handler 

To install the Thycotic Native Message Handler on a user’s computer, copy the ThycoticMessagingHost.exe and a settings.json file into a directory that is accessible (read access) to the end user (e.g. `C:\Program Files\Thycotic\Web Password Filler\`)

Once the ThycoticMessagingHost.exe and a settings.json file are copied to the user’s machine, you must register the ThycoticMessagingHost.exe with the browsers. To do this run ThycoticMessagingHost.exe with a `--register` command line option. This MUST be called before the Native Messaging handler will
interact with the Thycotic Web Password filler. Example (from a command window `C:\Program Files\Thycotic\Web Password Filler\ThycoticMessagingHost.exe --register`)

If you change the extension ID, you MUST update the settings.json to reflect the new extension ID. Each time you change the extension ID, you must run the `-–register` command line option again before the extension will be able to communicate to the native messaging host.

Changing other options or settings in the settings.json will automatically be reflected once the user launches their browser.

During the registration process, the Thycotic Native Message Handler will create three folders (Chrome, Edge, Firefox) which contain the “native messaging host configuration” information required by the browsers. Additionally, register entries are created for each browser in either the current user registry or the
local machine registry.

For example, `HKEY_CURRENT_USER\Software\Google\Chrome\NativeMessagingHosts\com.thycotic.wpf.host` with a default value that is the path to the “native messaging host configuration” file. If registering using the `EnableForAllUsers = true` option, you must run the registration as an administrator.

## Uninstalling the Thycotic Native Message Handler

To disable or remove the Thycotic Native Message Handler, use the `–unregister` option (for example `C:\Program Files\Thycotic\Web Password Filler\ThycoticMessagingHost.exe --unregister`). Once unregistered, the Thycotic Native Message Handler can no longer communicate with the Thycotic Web Password Filler.

## Configuration options

The settings can be managed through the Thycotic Native Message handler by modifying and deploying a settings.json file. The file is read by the Thycotic Native Message Handler and on request from the Thycotic Web Password Filler, passes the information to the Thycotic Web Password Filler. Once the Thycotic
Web Password Filler has the information, the Thycotic Web Password Filler updates the local storage with the new settings and configuration.

>**Note**: Aside from being able to manage the Thycotic Web Password Filler settings, the Thycotic Native Message handler provides a more robust method of storing the settings that are not impacted when the browse cache is deleted.

Each setting on the settings page can be set using “true” or “false” in the settings.json.

![](images/settings.png)

The Secret Server URL and Domain can be set by including strings (text wrapped up in quotations).

![](images/config.png)

Additionally, you can choose to hide these pages from the end user so that the settings and configuration options cannot be changed.

![](images/login.png)

## Site Exclusions and Exceptions

The Thycotic Web Password Filler is an “inclusive” extension. Any website that contains a username and password has the potential to have a secret retrieved from or stored in Secret Server. However, some sites are simply web forms that contain a username and password field. Registration forms for instance would not
require interaction or population of the username and password from the Thycotic Web Password Filler. The Thycotic Native Message handler allows you to add exclusions as well as exclusion exceptions so those sites you do not want the Thycotic Web Password Filler to interact with will be ignored. Add exceptions for any site you wish the Thycotic Web Password Filler to ignore. If there is an exception (e.g. To login to an application you want the Thycotic Web Password Filler to retrieve a secret for the login page, however you would like the Web Password filler to ignore every other page for that same site), add the specific page URL to the exclusion exception list.

To exclude all sites, a wild card can be used (`https://*` and\or `http://*`) and then simply add the sites where secrets are available (<https://MyCompanySite.com/login.aspx>) to the exclusion exception list.

## Settings.json Format

The settings.json is a json file. There are many online validators to ensure that the json is formatted correctly and we recommend that you validate your json prior to deployment.

Here is an example settings.json file that sets the Secret Server URL to `<https://SomeURL/SecretServer>`, the domain to “local” and enables all available options that are provided with the Thycotic Web Password Filler as well as hides the configuration and settings pages from the end users.

```
{

  "chromeExtensionId": "mfpddejbpnbjkjoaicfedaljnfeollkh",
  "edgeExtensionId": "kjldmpkefedgljefehmmfifbhnjngmbh",
  "operaExtensionId": "bpknpjofdmgfiiodcbdkdgannchkdmep",
  "firefoxExtensionId": "dd1e31d5-3623-45cb-b1ad-64074d36b360\@thycotic.com",
  "EnableForAllUsers": true,
  "ConfigSSUrl": "https://SomeURL/SecretServer",
  "ConfigDomain": "local",
  "HideConfigPage": true,
  "HideSettingPage": true,
  "SettingUserSSLogin": true,
  "SettingPrompToSave": true,
  "SettingShowPopup": true,
  "SettingHideReadOnlyFolders": true,
  "SettingEnableAutoPopulate": true,
  "Exclude": [
"\*",

    "http://endoftheinternet.com",

    "<https://www.MyCompanySite.com>",

"https://live.com/"

  ],

  "ExcludeException": [

    "https:// MyCompanySite.com/Login.html",

    "https://login.live.com/login.srf"

  ]

}
```

## Requirements

* .NET version 4.5.2
* Thycotic Web Password Filler version 2.0.3 and later

## Supported Browsers

* Chrome
* FireFox
* Edge Chromium
* Opera

Additional information regarding Native Messaging can be found at

* https://developer.chrome.com/extensions/nativeMessaging
* https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/Native_messaging
