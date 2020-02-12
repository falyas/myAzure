# Overview of Azure

## Architectures
### IaaS
- Virtual Machines
- Load balancing
- Developer manages data, operating system, and so on

### SaaS
- Ready made solutions

### PaaS (our focus)
- Active Directory access
- Make APIs and storage
- Active to SQL databases, web applications, and tables

# Web Applications on Azure

## App service creation
### Resource Groups
- Aggregate resources in one place
- A way to bundle together different resources
- A user can manipulate resources within a single resource group by applying a single change
- For example, a user can delete a resource group and this deletes all resources in the group
- It is helpful to make a separate resource group for a test application

### Different paths, same end
1. Use visual studio to develop your application, publish and deploy to azure from visual studio
2. Use visual studio to develop your application, use the deployment center in azure to setup and deploy your application

If you want to deploy your application to azure from visual studio, then use the same email account for azure portal email and visual studio. You'll also need to install the Azure development tools in visual studio, if you haven't already done so.

Here is a [quick tutorial](https://docs.microsoft.com/en-us/azure/app-service/app-service-web-get-started-dotnet)

Once you deploy your application, you can view stats about your application in the dashboard of that application, in the azure portal.

## Virtual Machines
### Availability set
- Selected once, and can't be changed
- It's recommended to use two machines for redundancy, and to meet 99.95% Azure SLA

### Public IP
- It's recommended to use the default
- Change the public IP, if necessary, for private corporate VPN

### Diagnostic storage accounts
- Set by default
- This is where log files go

### Running Summary
- Review cost per hour
- Check VM info, make sure it's the same type you initially selected

### Overview page of Virtual Machines
- Click 'connect' to download the virtual machine to your computer. Login using the same or different credentials, as those used in making the virtual machine. You now have a remote desktop.
- Check that visual studio on your virtual machine works as expected. Run a small test program.
- Go back to the azure virtual machine dashboard, you will notice a spike in activities.

### Shutdown virtual machines
- Go to the 'Virtual Machines' blade in your azure map portal account. Click the three dots next to the virtual machine you want to stop, right click, and select stop.
- The activities in the dashboard, of a stopped virtual machine, appear paused.
- Click delete near the top of the dashboard to delete the virtual machine.

## Azure Functions

### serverless
You don't need to manage any aspect of the server-side. Write some code, and tell azure to execute the code based on an event. Example of events: HTTP call, timer, Web Hook. A Web hook is an HTTP post when an event happens.

Azure function can be created directly in the portal or deployed from tools, such as, GitHub or visual studio.

### A type of web services
- managed differently
- smaller than microservices: nano scale
- Autonomous
- Run in the cloud without respect to any virtual machines

### Hosting plans
1. Consumption plan: Azure function are configured to incur a cost only for the execution time of the service. Execution time: total number of gigabytes for your application * total number of seconds * cost rate
2. App service plan: why use this when you have the Consumption plan?

### Functions Apps page
- The entry point for Azure Functions is the "Run" method.
- The schedule for the timer uses Cron. For the syntax of cron, go to [crontab.guru](https://crontab.guru), and get a syntax for your the value you want to set in the 'schedule' field.
- Run your code, you will see the log show at the bottom panel. You can also accesses this log file from Kudu.
- Get your Azure Function URL. Put "scm." after your Azure Function name in the URL. You should see the Kudu page. Go to "Debug Console" > "Log Files" > "Applications" > "Functions". Download the zip file, extract it, and you will see the same log files as you would see in the azure maps log console. Kudu log files update nearly every second.
- In the function app page within azure portal, click on "view files" to view all the files associated with this azure functions.
- Here's a challenge, make an azure function triggered by a webhook. Make a webhook in GitHub. Figure out a way to connect the azure function with a GitHub webhook. Let the webhook talk to the function each time the GitHub user makes a commit.
