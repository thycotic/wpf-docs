[title]: # (RegEx)
[tags]: # (WPF)
[priority]: # (61)
# RegEx in WPF

RegEx is a sequence of patterns specified in Secret Server templates and provided to be specified as __OtherUrls__ during account setup in Web Password Filler (WPF), allowing session recording on redirected websites.

When a user is logged into a website using a secret and session recording is enabled, WPF will record a session for that URL. If a user is redirected to another URL and session recording should continue for the redirected URL, those URLs can be added in the __OtherUrls__ field when the account is added.

Currently this field supports only URLs.

## Using RegEx in WPF

1. To add a new secret via WPF, select a Secret Server template that has the RegEx field.

   ![regex-1](images/regex-1.png "Add Account to Secret Server modal")
1. Click __OK__.
1. In the new Add Account to Secret Server dialog add the required details.

   ![regex-2](images/regex-2.png "Add Account to Secret Server with RegEx template selected")

   In the field __OtherUrls__,  enter any other URL for which session recording should enabled, in the event that the user is redirected to those URLs.  
1. Click __Add__.
