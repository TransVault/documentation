# Deploying an agent

The following steps describe how to deploy and authorize an agent.  All of these steps take place on the 'Agents' tab inside the Onboarding application.

**Note**: If an agent is deployed, but not authorized it will not be used by Onboarding.

## Generate a Key

The first step to deploying an agent is to generate a unique key for the installation. This is valid for 2 hours, and should be copied to your clipboard for use during the agent installation.


![Seed](images/agent-generate.png)

## Download the agent

The latest agent can be obtained and should be downloaded to the server where it is going to be installed.


![Seed](images/agent-download.png)

## Install the agent

During the installation you can specify the location where the agent is installed on the local machine. You must also provide the key which was generated inside the Onboarding application.

**Note**: If the key is more than 2 hours old, it will not work and a new one will need to be generated.

## Configure credentials

Depending on the role of the agent additional credentials need to be input. This activity is performed with the credentials manager. The name of these credentials (but not the credentials themselves) will be visible in the Onboarding interface allowing you to process different workflow steps under different credentials.

<screenshot needed>

## Authorize the agent

Once the agent has successfully started it will check-in with the Onboarding application. On the 'Agents' tab in the user interface you will be able to see the freshly installed agent. To allow the agent to be used for Onboarding select it in the table, and click the icon in the 'Authorized' column. A few seconds later the agent will be authorized for usage by Onboarding.

![Seed](images/agent-authorize.png)

## Add plugins

Depending on the role of the agent additional agent-side plugins can be added to the agent. These will be automatically downloaded and the functionality will be added to the agent which has been selected.

![Seed](images/agent-plugins.png)