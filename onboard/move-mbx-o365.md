# Moving a mailbox to Office 365

A typical workflow template to move an on-premises mailbox into Office 365 might contain the following steps.

1) **Communication Step - *Mail User*.**  
Advise the user in advance that their mailbox will be moved into Office 365 in X number of days.  This step requires a MSG template file and can contain personalised details like FirstName and LastName to ensure the email is tailored for the end user.

2) **Communication Step - *Mail administrator*.**  
Send an email to a specific administrative email address confirming that the user has been successfully notified.  This step also requires a MSG template file.

3) **Wait Steps  - *Wait Time*.**  
Set a timed delay for X amount of days/hours etc before the next step is processed.

4) **Office 365 - *Preflight primary to cloud*.**  
Run checks against the on-premise Exchange to ensure the account exists and the email address is valid.

5) **Office 365 - *Move primary to cloud*.**  
Initiate the move of the users mailbox into Office 365.

6) **User and License Steps - *Assign a license*.**  
Assign an Office 365 license to the recently created users mailbox so that it can be accessed.

7) **Communication Step - *Mail User*.**  
Email the user and advise them that their mailbox has now been moved into Office 365, and that they will need to restart Outlook.

You can add in more wait steps or communication steps as are required for your specific project, but this process forms a simple framework for moving a users mailbox into Office 365.
