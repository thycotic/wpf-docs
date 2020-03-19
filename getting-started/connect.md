[title]: # (Connecting with Secret Server)
[tags]: # (WPF)
[priority]: # (30)
# Connecting with Secret Server

After installation, you must configure WPF to connect with Secret Server before logging on the Website. You can use the Configuration tab on WPF to configure it with the Secret Server instance of your choice.

To connect WPF with Secret Server:

1. Open Google Chrome or any other supported browser.
1. In the upper-right corner of the browser, click the __Password Filler__ ![image-20191205103957493](images/image-20191205103957493.png "WPF icon") icon. The WPF login window appears:

   ![images/image-20191205101713805](images/image-20191205101713805.png "Login information")
1. Click the __Configuration__ tab:

   ![image-20191205101911389](images/image-20191205101911389.png "Configuration information")
1. In the __Secret Server URL__ field, type your Secret Server URL. For example: `https://myserver/secretserver/`
1. In the __Domain__ field, type the domain of Secret Server. This only applies if you set up Secret Server to use a domain otherwise it is Local by default. This should match the options configured in Secret Server for this sign in page:

   ![connect-5](images/connect-5.png "Example of the domain information set up for signing into Secret Server")
1. Click the __Save__ button. A confirmation message appears. WPF's connection settings are now saved.
