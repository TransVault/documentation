# Enabling mailbox auditing
By default even when Exchange auditing is enabled, very little information is collected by Microsoft. If you want to gain insight into more details about user activity within Exchange then additional configuration via PowerShell is needed. You can do that as follows:

# Connecting to Office 365 PowerShell
Each of the scripts on this page require that you create a session to Office 365 PowerShell.  This is accomplished as follows:

1. Launch PowerShell.

2. Enter the following

	```
	$UserCredential = Get-Credential
	$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
	Import-PSSession $Session
	````

When the above runs, you will be prompted for credentials to use to make the connection.

# See who has auditing enabled
Issue the following command in PowerShell:

```
Get-Mailbox -ResultSize Unlimited -filter {AuditEnabled -eq $true} | fl name, userprincipalname
```

# See which auditing options are enabled
Issue the following command in PowerShell:

```
Get-Mailbox -ResultSize Unlimited -filter {AuditEnabled -eq $true} | fl name, userprincipalname, audit*
```

# Enable auditing for one mailbox
Issue the following command in PowerShell:

```
Set-Mailbox -Identity "a-user-upn@somedomain.com" -AuditEnabled $true
```

To enable specific events for auditing the following can be issued:

```
Set-Mailbox -Identity "a-user-upn@somedomain.com" -AuditOwner @{Add="MailboxLogin","HardDelete"}
```
		
# Enable auditing for multiple mailboxes
Issue the following command in PowerShell to enable mailbox auditing on all mailboxes in your Office 365 tenant:

```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -AuditEnabled $true
```


**Note**: More details are available on this [link](https://support.office.com/en-us/article/enable-mailbox-auditing-in-office-365-aaca8987-5b62-458b-9882-c28476a66918)