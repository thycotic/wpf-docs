[title]: # (Login)
[tags]: # (WPF, troubleshooting)
[priority]: # (82)
# WPF Login

Are you logged into WPF?

Currently you do need to log into WPF separately from SS. This is because we use the REST APIs to communicate back to SS. This design is also to allow users to log into WPF but NOT SS, which would let them go to a site and still access Secrets without using Secret Server directly.

You can tell at a glance if you are logged in or not by the icon in the browser.

1. Not Logged in

   ![](images/75f035d8078d87bccb813970fc4b4eaa.png)
1. Logged in

   ![](images/b8c444ca436812a3e466b42bc1231419.png)

## Login Method

There are two different Login methods, which login method is being used?

1. The two login methods are Username/Password and Login through Secret Server (for SAML). Refer to the Secret Server documentation on [SAML](../../ss/10.8.0/authentication/saml/index.md).

<!--Are there other authentication processes involved in the normal Secret Server Login? For example, are they using DUO? Okta?
-->
