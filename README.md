<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Post-Install Configuration</h1>
This tutorial outlines the post-install configuration of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- osTicket
- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Prerequisites and Links</h2>

- <a href="https://github.com/agarcia-it/osticket-prereqs">osTicket-prereqs</a>
- osTicket Admin Login: http://localhost/osTicket/scp/login.php (requires completion osTicket-prereqs to function properly)

<h2>Post-Install Configuration Objectives</h2>

- Set up the osTicket Environment
- Examine Roles, Departments, Teams, Admins, Agents, Users, SLA's, and Help Topics

<h2>Configuration Steps</h2>

<p> 1.) <strong>Create a Supreme Admin role - </strong>Log into osTicket and navigate to the Admin Panel at the top-right. From there, navigate to Agents -> Roles. Here we can create a "Supreme Admin" role that has complete read/write access, as well as the ability to open, close, assign, modify, and delete tickets within osTicket. Name the role "Supreme Admin" and select all of the check boxes on the Permissions tab. Click Add Role when finished to create the Supreme Admin role.
</p>
<p>
<img src="https://i.imgur.com/QSnfZEz.png" height="70%" width="70%"/>
</p>
<p>---------------------------------------------------------------------------------------------------------------------------------</p>
<br />

<p> 2.) <strong>Create a System Administrators department - </strong>From the Admin Panel, navigate to Agents -> Departments and click + Add New Department. Name the new department "System Administrators" (or something to that effect) and click "Create Dept". Defining a System Administrators department allows us to identify which members of the organization have admin access within osTicket. 
</p>
<p>
<img src="https://i.imgur.com/T7yDs6e.png" height="70%" width="70%"/>
</p>
<p>---------------------------------------------------------------------------------------------------------------------------------</p>
<br />

<p> 3.) <strong>Create support teams - </strong>From the Admin Panel, navigate to Agents -> Teams and click + Add New Team. For this example we will create two new teams: "Level II Support" and "Level III Support" (Level I Support is a default support team on osTicket). Creating multiple support tiers allows the organization to properly escalate tickets to the appropriate staff during the ticket life cycle. Additionally, teams can be created to solve specific issues that an organization might face. For example, if a complex problem were to arise, an "A" team comprised of some of the best talent across different departments in order to solve the problem. For this walkthrough, we will stick with Tier I-III Support.
</p>
<p>
<img src="https://i.imgur.com/aBmgm8B.png" height="85%" width="85%%"/>
</p>
<p>---------------------------------------------------------------------------------------------------------------------------------</p>
<br />

<p> 4.) <strong>Create Agents - </strong>Agents are essentially the operators of the the ticketing system. They would be the help desk staff within the organiztation working and resolving tickets. To create new agents, start in the Admin Panel -> Agents and click + Add New Agent. Enter the credentials for the an agent "Jane Doe" (for the purpose of this walkthrough we will use arbitrary credentials, but real credentials should be used if this ticketing system was to be implemented for real-world purposes). Click on "Set Password" and create a password for Jane Doe. (For the purpose of this walkthrough, we will uncheck "Send the agent a password reset email" and "Require password change at next login". This would be considered bad practice in a real world application, but we simply want to be able to log into our mock Agent accounts without having to reset passwords at this time). Navigate to the Access tab and select the Primary Department and Role for Jane Doe (System Administrators and Supreme Admin). Additionally, give Jane Doe extended access to the Support Department as a Supreme Admin. You can also assign Jane Doe to a Team - I assigned them to Tier III Support. Create another user "John Doe" and follow the same instructions (I assigned them to Tier II Support). We can add ourselves to the System Administrators department and Supreme Admin role and Tier III Support Team.
</p>
<p>
<img src="https://i.imgur.com/AbhrDUQ.png" height="85%" width="85%%"/>
</p>
<p>---------------------------------------------------------------------------------------------------------------------------------</p>
<br />

<p> 5.) <strong>Create Users - </strong>Users consist of those who will need to access the ticketing system to submit tickets. This could include employees who work in a non IT-related department such as accounting or sales, who need to submit tickets for IT-related problems. This time, navigate to the <strong>Agent Panel</strong> -> Users and click + Add User. I created two users, Karen Doe and Ken Doe, with emails of "karen@osticket.com" and "ken@osticket.com" (these users and emails are abritrary for the purpose of this walkthrough). Now we have users who will act as employees that submit tickets for Help Desk to work on.
</p>
<p>
<img src="https://i.imgur.com/j4ronVt.png" height="85%" width="85%%"/>
</p>
<p>---------------------------------------------------------------------------------------------------------------------------------</p>
<br />

<p> 6.) <strong>Configure SLA's - </strong>According to <a href="https://en.wikipedia.org/wiki/Service-level_agreement">Wikipedia</a>, "A service-level agreement (SLA) is a commitment between a service provider and a customer. Particular aspects of the service – quality, availability, responsibilities – are agreed between the service provider and the service user." For the purpose of this tutorial, we will use them to categorize different ticket severities, and the time frame from which they are expected to be resolved. Each organization defines their own SLA's, and for this tutorial we will define them with simplified requirements. Navigate to Admin Panel -> Manage -> SLA and click + Add New SLA Plan. Create three different SLA Plans:
<br /><br />
  -Name: SEV-A, Grace period: 1 hour, Schedule: 24/7<br />
  -Name: SEV-B, Grace period: 4 hours, Schedule: 24/5<br />
  -Name: SEV-C, Grace period: 8 hours, Schedule: business hours
 <br /><br />
Now we have different SLA's for different severity tickets. SEV-A is the highest priority, should be solved within 1 hour (this might be unrealistic, but is only for example purposes), and should be worked on regardless of the time of day, any day of the week. SEV-B is the second highest priority, should be solved within 4 hours, and should be worked on regardless of the time of day, on weekdays only. SEV-C is the lowest priority, should be solved within 8 hours, and should only be worked on during regular business hours.
</p>
<p>
<img src="https://i.imgur.com/D72YkMY.png" height="85%" width="85%%"/>
</p>
<p>---------------------------------------------------------------------------------------------------------------------------------</p>
<br />

<p> 5.) <strong>Configure Help Topics - </strong>Help Topics are pre-configured categories of issues that end-users might experience. They can be relevant to specific software or devices that a company may use, and give help desk professionals the ability to further organize and respond to tickets. To create a new Help Topic, navigate to: Admin Panel -> Manage -> Help Topics and click + Add New Help Topic. Create 4 new Help Topics (Business Critical Outage, Personal Computer Issues, Equipment Reset, and Password Reset) with default settings.
</p>
<p>
<img src="https://i.imgur.com/88aOVdt.png" height="85%" width="85%%"/>
</p>
<p>
We now have osTicket set up and are ready to service some mock tickets.
</p>
<br />
