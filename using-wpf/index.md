[title]: # (Using WPF)
[tags]: # (WPF)
[priority]: # (4)
# Using WPF

Once WPF is set up and you are logged into Secret Server, you can use WPF to log in to websites for which Secrets are managed via Secret Server. 

Refer to [Creating a Secret for a Website](create.md) if you need to add new accounts.

## Log in to a Website

1. Take a quick look at your WPF button on your browser's button bar. If it is grayed out, you will need to sign into Secret Server and return here.

1. Navigate to the website you want to access. Note there is a green Thycotic logo in the site's account name text box:

   ![image-20191205162559891](images/image-20191205162559891.png "Log in modal")

   >**Note**: If you are signed into WPF and do not see the green check in the username text box, please try refreshing the web page to make it appear.

1. Click the Thycotic logo. A WPF popup opens and one of two things can happen:

   - If you have one or multiple existing secrets for a site, a popup will open displaying all of the available secrets available for the site. For instance:

     ![image-20191208145851919](images/image-20191208145851919.png "Sign in as modal")

   - If you have no secrets related to the site, then a popup will open to give you the option to add a new secret:

     ![image-20191205162836870](images/image-20191205162836870.png "Add a secret modal")

   If you see the second possibility, you need to set up a secret for that website. See [Creating a Secret for a Website](create.md).

1. Click the button for the desired secret, and you are signed in.
