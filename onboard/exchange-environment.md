# Configuring Exchange environment

Once the agent has been installed (typically this would be the Exchange On-premises server which would act as the PowerShell host where the exchange management shell is located), you will be presented with various tabs.

The Exchange tab is where you will find all the settings and configuration required with regards to the Exchange server.

**Environment name -** This is a memorable label / name that you can apply that helps you to distinguish the environment being referenced.

**Exchange PowerShell Host -** This should be set to the server that contains the Exchange management shell and contains the PowerShell host for the environment.

**Agent -** This is the server where the agent is installed.

**Credentials -** The credentials are those of either the exchange admin or domain admin.

## Scheduled jobs

At the bottom of the Environment tab you will see the scheduled job list. You can edit a task by clicking on the edit icon in the list of available hosts.

The jobs available are as follows:

**TestMRSHealth -** This job tests / checks the MRS health of an instance of the Microsoft Exchange Mailbox Replication service.

**GetMigrationEndpoints -** GetMigrationEndpoints will retrieve all available migration endpoints within a Hybrid Environment.

**GetRemoteMailbox -** The GetRemoteMailbox job will run PowerShell commands in order to establish which mailboxes are in O365.

**GetExchangeServers -** This job will get all the On-premises Exchange servers.

**GetOnPremMailbox -** When this job runs it will fetch all information related to the On-premises mailboxes.

**GetOnPremMailboxStatistics -** This job will get all On-premises Mailbox Statistics of the On-premises Mailboxes.

**GetOnPremPersonalArchiveStatistics -** This job will fetch all On-premises Personal Archive Statistics (for example number of items and how many folders etc).