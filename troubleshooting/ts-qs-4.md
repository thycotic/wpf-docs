[title]: # (Problem Presentation)
[tags]: # (WPF, troubleshooting)
[priority]: # (82)
# Behavior/Problem Presentation

If reporting problems or asking for help with WPF, the more information that can be provided about the actual behavior experienced, the faster a resolution can be found.

All of previous troubleshooting topic help narrow things down. The more specific, the better.

Some examples:

1. Is the user not able to login to WPF?

   * Are they getting any error messages?
   * Are they logging in and then getting logged out again?
   * What authentication types are enabled and are they using them?
   * Is the "Login" button greyed out?
   * Is the Secret Server URL (and optional: Domain) entered in the "Configuration" tab?
   * Can they reach the Secret Server UI from the same machine/browser?

1. Is the Secret not being displayed on the site?

   * Is there only one Secret for the site?

     1. If Yes, then are all the Secret not being displayed? Or just some Secrets not displayed?
   * Does the logged in account have access to that Secret?

1. Are the credential fields populated correctly?

   * If No, what fields are being populated?
   * Is the green Thycotic check logo displayed in the Username/email field?

     1. We ONLY display this in the Username or email fields, it is NOT displayed in the password field
   * Are the right-click options available in any of the login fields?
   * Which fields are not populated?
   * Are they populated and put in the wrong spot?
   * Does the site require a drop-down or other action to be taken before the credential fields are available?
   * Does the site use a multi-page login (like O365)? Or single page log (like LinkedIn)?
1. Is it some kind of visual issue on the page?

   * Is the green Thycotic log visible?
   * Is the green Thycotic logo in the wrong place on the page?
   * Is the page displaying as blank?
   * Are the icons for the Secrets not showing up?

1. Is it a newly added Secret that is not showing up?

   * When a Secret is added in Secret Server or in WPF there are times when it might not appear immediately on the site. WPF relies on the Secret being indexed in SS, and it typically takes some time for that index to happen (depending on the size of the environment).
   * Usually if you wait a few minutes and refresh the page you should be able to see it appear.
   * In Release 1.1.0 of WPF a short-term caching option was introduced. This is indicated by a refresh button on the drop down for the credentials. This caching means that we should keep the Secret in memory for that browser session so we don't have to wait for Secret Server to index it.
1. Is there some kind of other issue happening? If so, what?
