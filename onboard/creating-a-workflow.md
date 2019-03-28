# Creating a Workflow

A workflow is an essential element of onboarding. It consists of a number of workflow steps which will be executed in order to process a user or a group of users.

The workflow template system is flexible and can be used to create simple and complex workflows to suit the particular onboarding requirements. In order to get started, we'll go through an example of creating a simple workflow to send out emails to a user and an administrator.

All of the workflow template activities take place on the Workflows tab and are described below.


## The Canvas

The main workflow template editor window looks like this:

![Seed](images/workflow-canvas.png)

In here you can retrieve previously saved templates, as well as configure new ones.  You begin by dragging and dropping workflow steps on to the canvas. You can arrange them however you like, but we prefer to see them put into a logical order to make following the workflow eaier.

## Communication steps

In this simple example we will expand the 'Communication steps' group of workflow steps and drag and drop two communication steps. These are shown below:

![Seed](images/workflow-comms.png)

## Introducing a delay

For our example we want to introduce a few minutes delay between the email steps. This is achieved by dragging and dropping a 'Wait steps' workflow step. We now have a template like this:

![Seed](images/workflow-addingwait-1.png)

## Joining the steps

The steps in a workflow need to be joined together to show the logical flow of the process. That's easy to do. Click and drag from the text of one workflow step, to the next in the sequence. Repeat that process for each step, and you will see this:

![Seed](images/workflow-joining.png)

## Configuring the steps

Some of the steps have configuration options available to them. That's shown by the small cog-icon on the workflow step when it's on the canvas. If you click that it will show a pop-up and allow you to configure the steps.

For our example on the user communication step, we can configure a template email to send to the user. Similarly in the administration communication step we can configure a template to send, and we can configure who the email will go to. Lets choose your own email address for that.  Lastly, our wait step allows us to configure how long we want to wait.  Lets choose 5 minutes for that step.

![Seed](images/workflow-addingwait-2.png)


## Finally, saving the workflow

The final step is to save the workflow template. We can give the template a friendly name which will help us when it comes to mapping users.  

**Note**: If there is a problem with the workflow a pop-up will appear giving your advice on how to fix it.

# Moving a mailbox to Office 365

**Coming Soon** We describe a very simple workflow template for moving a mailbox from on-premises to Office 365, in this section.