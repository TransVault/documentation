# Configuring TransVault environment

In this tab you can configure the TransVault scheduled jobs that relate to the TransVault Migration server. These jobs can be run at any time from the scheduled jobs window.

**Environment name -** This is a memorable label / name that you can apply that helps you to distinguish the environment being referenced.

**SQL Server -** This should be set to the SQL Server that hosts the TransVault database.

**Database name -** The TransVault database default (?TBD?).

**Agent -** This is the server where the agent is installed.

**Credentials -** The credentials are those of either the exchange admin or domain admin.

## Scheduled jobs

At the bottom of the Environment tab you will see the scheduled job list. You can edit a task by clicking on the edit icon in the list of available hosts.

The jobs available are as follows:

**GetTVConnections -** This job fetches the configured connections in a TransVault Environment.

**GetTVMailboxes -** Fetches the mailboxes/archives seen in a TransVault Environment.

**GetTVPerformance -** Fetches the performance statistics for a Migration Queue.

**GetTVQueues -** Fetches the configured queues in a TransVault Environment.

**Agent notes** : When installing the agent, it&#39;s important to note that you must have one agent per datacentre. The agent is forest specific as well i.e. if you have more than one Exchange server in different forests in different locations, then each one will need its own agent. Likewise, in a cross domain scenario, this would also require multiple agents.