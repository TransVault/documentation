# Frequently Asked Questions

Below you will find a list of the most commonly asked questions regarding OnBoard.

**Q** - Which firewall ports are required for OnBoard?  
**A** - The Onboard agent only uses HTTPS outgoing (port 443)

**Q** - What pre-requisites are there if I want to use OnBoard?  
**A** - A mandatory requirement is that the OnBoard agent needs access to an on-premises AD environment.  You must also have a tenant within the TransVault platform.

Depending on your environment you might also need to whitelist the following sites and/or allow access through your firewall.  

*.transvault.com  

Geotag APIs  
http://api.ipstack.com  
http://checkip.amazonaws.com  
https://icanhazip.com  
https://api.ipify.org  
https://ipinfo.io  

**Q** - If I have plugin updates pending in addition to an agent update, do I need to update the agent version first?  
**A** - Plugin updates are backwards compatible so whilst there is no specific requirement to update the agent as well (if applicable), we would recommend time is scheduled outside of workflows being run so that all can be updated to the latest versions available.

**Q** - How does OnBoard treat non-conventional user mailboxes (Shared and Resource mailboxes)?  
**A** - Resource and shared mailboxes are treated the same way as a regular mailbox. The most important thing is for the mail attributes of such object to be available in office 365.This is made possible with AAD connect.

**Q** - Can I use OnBoard to migrate data into targets other than Office 365?  
**A** - No.  OnBoard has been specifically developed to enhance the workflow for migrations of on-premises mailboxes and/or archives into Office 365.

**Q** - If I cannot use OnBoard to migrate archive data into alternatives like PST files but am part way through a migration, what are my options?  
**A** - If you have a requirement to migrate some of your archive data out to PST files or other alternative output, you would need to complete these steps using Migrator in the usual way.

**Q** - Your "Move to Cloud" Step is stuck at a certain percentage for too long e.g. usually a day or more.  
**A** - Check the OnBoard client logs, PowerShell tab for exceptions like **Check Service health** in reporting.
Useful powershell cmdlets: **get-moverequest** to check the status of the move request. If you want a detailed status report,
run **get-moverequeststatistics**
. In both cases always add a pipe < | FL >.

e.g.
```
Get-MoveRequest -Identity  usera@company.com | FL
Get-moverequeststatistics  -Identity  usera@company.com  | FL
```
