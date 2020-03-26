# OnBoard

## Getting started

There are three stages to go through to get started with TransVault Onboard, and they're described in the sections below:

### Agents and configuration

At least one agent has to be deployed to an on-premises server in order to use the OnBoard features. Don't worry though, it's really easy to setup and configure. The instructions are covered in this [section](onboard.md#deploying-an-agent).

### Creating a workflow

After the agent is properly configured the next step is to create a workflow. The instructions are covered in this [section](onboard.md#creating-a-new-workflow).

### Mapping the first user

The final step in using OnBoard is to map a test (or pilot) user. The instructions are covered in this [section](onboard.md#mapping-a-pilot-user).

## Deploying an agent

The following steps describe how to deploy and authorize an agent.  All of these steps take place on the 'Agents' tab inside the OnBoard application.

Before installing the agent you must ensure that [PowerShell 6.2](https://github.com/PowerShell/PowerShell) is installed on the server where the agent is to be deployed.

To install PowerShell Core on Windows using a single command line from Windows PowerShell:
```
iex "& { $(irm https://aka.ms/install-powershell.ps1) } -UseMSI"
```


**Note**: If an agent is deployed but not authorized, it will not be used by OnBoard.

### Generate a Key

The first step to deploying an agent is to generate a unique key for the installation. This is valid for 2 hours, and should be copied to your clipboard for use during the agent installation.


![Seed](images/agent-generate.png)

### Download the agent

The latest agent can be obtained and should be downloaded to the server where it is going to be installed.


![Seed](images/agent-download.png)

### Install the agent

During the installation you can specify the location where the agent is installed on the local machine. You must also provide the key which was generated inside the Onboard application.

**Note**: If the key is more than 2 hours old, it will not work and a new one will need to be generated.

### Configure credentials

Depending on the role of the agent additional credentials need to be input, this can be done via the Credential Editor exe which can be found in the folder where the OnBoard agent was installed. The name of these credentials (but not the credentials themselves) will be visible in the Onboard interface allowing you to process different workflow steps under different credentials.

![Credentials](images/credential_editor.png "Credential Editor")

### Authorize the agent

Once the agent has successfully started it will check-in with the Onboard application. On the 'Agents' tab in the user interface you will be able to see the freshly installed agent. To allow the agent to be used for Onboard select it in the table, and click the icon in the 'Authorized' column. A few seconds later the agent will be authorized for usage by Onboarding.

![Seed](images/agent-authorize.png)

### Add Plugins

Depending on the role of the agent additional agent-side plugins can be added to the agent. These will be automatically downloaded and the functionality will be added to the agent which has been selected.

![Seed](images/agent-plugins.png)

## Creating a New Workflow

A workflow is an essential element of TransVault OnBoard. It consists of a number of workflow steps which will be executed in order to process a user or group of users.

The workflow template system is flexible and can be used to create both simple and complex workflows to suit the particular OnBoard requirements. In order to get started, we'll go through an example of creating a simple workflow to send out emails to a user and an administrator.

All of the workflow template activities take place on the Workflows tab and are described below.


### The Canvas

The main workflow template editor window looks like this:

![Seed](images/workflow-canvas.png)

In here you can retrieve previously saved templates, as well as configure new ones.  You begin by dragging and dropping workflow steps on to the canvas. You can arrange them however you like, but we would recommend placing them into a logical order to make following the workflow easier.

## Communication steps

In this simple example we will expand the 'Communication steps' group of workflow steps and drag and drop two communication steps. These are shown below:

![Seed](images/workflow_email.png "Email Steps")

### Introducing a delay

For our example we want to introduce a few minutes delay between the email steps. This is achieved by dragging and dropping a 'Wait steps' workflow step. We now have a template like this:

![Seed](images/workflow-addingwait-1.png)

### Joining the steps

The steps in a workflow need to be joined together to create the logical flow of the process. Simply click and drag from the text of one workflow step, to the next in the sequence. Repeat that process for each step, and you will see the following:

![Seed](images/workflow-joining.png)

### Configuring the steps

Some of the steps have configuration options available to them. That's identified by the small cog-icon on the workflow step when it's on the canvas. If you click that it will show a pop-up and allow you to configure the required elements for that specific workflow step.

For our example on the user communication step, we can configure a template email to send to the user. Similarly in the administration communication step we can configure a template to send, and we can configure who the email will go to. Lastly, our wait step allows us to configure how long we want to wait e.g. 5 minutes.

![Seed](images/workflow-addingwait-2.png)


### Finally, saving the workflow

The final step is to save the workflow template. We can give the template a friendly name which will help us when it comes to mapping users.  

**Note**: If there is a problem with saving the workflow a pop-up will appear giving you advice on how to fix it.

## Moving a mailbox to Office 365

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

You can add in more wait steps or communication steps as required for your specific project, but this process forms a simple framework for moving a user's mailbox into Office 365.

## Mapping a pilot user

The process of assigning a workflow to a user is called mapping. This step can be done on individual users, or hundreds of users.

This process takes place on the Mappings tab in the user interface.

### Finding a user

The mappings page shows a list of your on-premises users. You can use the search box to quickly locate the user you wish to process.  Once you've located the user, select the checkbox next to that user, and click on the 'Map' button above the data grid.

**Note**: You cannot map an already mapped user.

### Mapping the user

The process for mapping a user is simple. You can give this chosen batch a name - that's useful for tracking purposes. You pick a workflow template, and a priority and you can even add a comment for the batch which will help later if someone has questions around the users in the batch.

### What happens now?

The mappings page will reflect the selections and mapping you have created. In the background TransVault OnBoard will perform all the necessary steps in your chosen workflow, and the user interface on the mapping and batches page will be updated to show the current status.

### Batching

Processing one user as we've done here is useful if you want to test the process of onboarding with your chosen workflow. Once the testing is done you will want to begin processing your user population in batches.

## Batching

Batching is an important step in onboarding lots of users. We've added the ability to the Onboarding application to setup batches manually, as well as being able to pick, use and customize automatically created batches based on groups.

All of this takes place on the Batches tab in the application, and is described below.

### List of batches

The top of the batches tab shows you batches that have already been created. Here you can perform operations on those batches such as enabling or disabling them from migration. You can also see the priority of the batch, how many users are in the batch,  whether the batch has already finished onboarding and much more.

### Selecting a batch

If a batch is selected in the top data table, then the bottom of the screen shows more details about users which are in that batch including the workflow that they are assigned and the status.

## Groups

You can create a new group by selecting the "Add a new group" button.

![New group](images/add_a_new_group.png "Add a new group")

Once selected you have a few options for creating your group.

![Creation](images/group_creation.png "Group creation")

- Method:
 - **Automatic** - Create groups based upon specific Active Directory properties e.g. Department
 - **Manual** - Create a manual group based upon an LDAP query (dynamic) or a static list of users (Comma separated UPNs or a CSV import file containing  a list of UPNs)

### Removing Groups

If you need to remove any manually created groups this can be done via the **Settings** option on the left hand pane.  Once selected you need to select the **"Groups"** tab.  
**Note** - Any group that has a description of "automatically created" was created by OnBoard as part of the batch creation process, so must not be deleted.

### Editing Groups

From within the same screen you can add users to an existing group by selecting the group in question, then selecting the ![Add](images/add_user.png "Add") button, and providing the UPN of the user to be added.

If you need to remove a user from a group you can follow the same steps as above, select the user in question and press the ![Add](images/remove_user.png "Remove") button.

## Monitoring progress

There are three places that the progress of a mapping and of the overall OnBoard project can be seen, these are described below.

### Overview

This tab gives an overall view of the progress of the migration.

From here you can easily check the progress of your existing mappings, organisation progress as a whole as well as statistics around batches run over a period of time.

### Batches

This tab gives summary information relating to batches that have been created in the OnBoard project, their overall status as well as further details about individual users within a batch.

### Mappings

The mappings tab gives details about individual users that have been processed or are being processed. If a user is selected you can quickly see the individual steps that have been performed i.e. which ones have been completed, current step in progress or whether any steps have failed.  

![Seed](images/workflow-steps.png "Workflow Steps")
