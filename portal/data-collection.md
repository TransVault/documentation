# Data collection

## Collection by consent
When you launch our Advanced Office 365 Reporting for the first time a short wizard will guide you through additional information 
which we need to collect.

The most important part of this step is that a Global Administrator for your Office 365 tenant needs to approve our application. This
process is called **providing consent**, or **consenting**.

This is a standard procedure for applications built to work alongside Office 365. If you are a global administrator you can provide
the necessary consent, and move on in the wizard. If you are not a global administrator you can provide the email address of one, we will
email that user and ask them to click on a link which will grant the consent. You will then be able to continue with the wizard.

## What does all this mean?
By following this Microsoft recommended method of providing consent, it is not necessary to store credentials in order to gather 
data for many of the reports which are available in the product.  Using the consent we can listen to various Microsoft data streams
relating to your tenant and using that collected metadata we can begin to show you reports and auditing information relating to your tenant.

## Additional credentials
During the wizard you will notice that we do ask for credentials. Those credentials are stored securely and used to obtain further
information, using PowerShell, to provide even more reports for you.  

If you don't provide credentials certain reports won't have data in them, but there will be a friendly reminder telling you. 
Credentials can be entered later, and the reports will be available from then.