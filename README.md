<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Post-Install Configuration</h1>
Hey there! This is a guide on how to configure osTicket, an open-source help desk ticketing system, after the installation process.<br />

<b>Note:</b> To follow along with this guide, make sure you have completed the prerequisites and installation steps described in my previous demonstration, "Prerequisites and Installation".  The notes and screenshots below will guide you visually through the steps involved and then further on highlight some or all of the material.


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)
- [osTicket Documentation](https://docs.osticket.com/en/latest/index.html)

<h2>Operating Systems Used </h2>

- Windows 10</b> (22H2)


<h2>Post-Install Configuration Objectives</h2>
Create and Configure Roles
Create and Configure Departments & Teams
Create and Configure Agents (workers) & Users (clients)
Configure SLA (Service Level Agreements)
Configure Help Desk Topics
<h2>Configuration Steps</h2>
<h3>&#9312; Prerequisites and Installation</h3>
This demonstration assumes a virtual machine is established with the prerequisite files installed for working osTicket. </br>
Credentials and configurations that will be used in this demonstration can be found in "Prerequisites and Installation". </br>

<hr>
<h3>&#9313; Admin Panel - Roles, Departments, Teams, & Agents</h3>
On the web browser (Microsoft Edge), go to the Help Desk Login Page and sign into your osTicket Help Desk credentials (this example uses username dennimun / ostuser@email.com).
Help Desk Login Page -- http://localhost/osTicket/scp/login.php

![image](https://github.com/Dennimun/post-install-config/assets/146505956/75d06cf2-28ed-48c7-bba1-bb4d88b5b432)


Currently at the Agent Panel, click on "Admin Panel" at the top-right of the page.

![image](https://github.com/Dennimun/post-install-config/assets/146505956/212fb6af-691f-4756-99ff-c0d1cf53ad94)



Click on the "Agents" tab > "Roles" > "Add New Role".

![image](https://github.com/Dennimun/post-install-config/assets/146505956/714fdb6f-36d7-4bc3-9a7b-65f65a4ba33a)


"Roles are the permissions granted to Agents per Department that they have access to."

In the Definition tab, type any Role name of your choice (this example uses Supreme Admin).
This role will be given all permissions.
Then, click on the Permissions tab.

![image](https://github.com/Dennimun/post-install-config/assets/146505956/f68775b8-a892-4c07-8dcb-c59b5342311f)


In the Permissions tab, under the Tickets category, checkmark ALL boxes.
Go through both Tasks and Knowledgebase categories and checkmark ALL boxes as well.
Once done, click "Add Role".

![image](https://github.com/Dennimun/post-install-config/assets/146505956/2b9b63d3-d38f-4300-be24-a67bcda1b780)


Now we've created a Super Admin role with all permissions granted. Next, we'll create a Department.

Currently in the Agents tab, click on the "Departments" category.
Click "Add New Department".

![image](https://github.com/Dennimun/post-install-config/assets/146505956/36412be2-5ebe-4ed1-8214-aa4ae87ceecb)


Create a Department name of your choice (this example uses System Administrators).
Skip everything else for now and click "Create Dept".

![image](https://github.com/Dennimun/post-install-config/assets/146505956/896e595c-6fd4-4ace-875a-ce1fd75b360e)


Next, we'll move onto creating a Team. <br>
"Teams allow you to pull Agents from different Departments and organize them to handle a specific issue or user via a Help Topic or Ticket Filter."

Currently in the Agents tab, click on the "Teams" category.

Click "Add New Team".

![image](https://github.com/Dennimun/post-install-config/assets/146505956/c16ef071-bfc4-4db3-a3cf-856de71aaaec)


Create a Team name of your choice (this example uses Level II Support).
Click "Create Team".

![image](https://github.com/Dennimun/post-install-config/assets/146505956/7c6acdea-f0d6-4589-826a-c6409aa980ad)


Currently in the Agents tab, click "Agents" category.

![image](https://github.com/Dennimun/post-install-config/assets/146505956/113b3c75-d3a7-498e-bc64-1cf3a90ae840)


Create the required credentials for this user that are in bold:
First Name (this example uses Jane).
Last Name (this example uses Doe).
Email Address (this example uses jane.doe@osTicket.com).
Username (this example uses jane.doe).
Click "Set Password" and a windows prompt will appear:
Uncheck "Send the agent a password reset email".
Create a password for this user.
Uncheck "Require password change at next login".
Click "Set".

![image](https://github.com/Dennimun/post-install-config/assets/146505956/1ffa4b2b-e3a2-4e93-88e2-34cb3db5ff11)


Click on the "Access" tab:
Assign this user the Department that we created (this example uses System Administrators).
Assign this user the Role that we created (this example uses Supreme Admin).
Under Extended Access, assign this user the "Support" department with the "Supreme Admin" role.
Click "Save Changes".

![image](https://github.com/Dennimun/post-install-config/assets/146505956/ad4bffb1-006f-47b6-a97b-c98c7e465acd)


Click on the "Teams" tab:
Assign this user the Team that we created (this example uses Level II Support).
Once done, click "Create".

![image](https://github.com/Dennimun/post-install-config/assets/146505956/840ed6c6-5133-4b86-bed0-aded0f4769e4)


Create another Agent following the steps, however assign it to a different Role and Department.</br>
This example creates Agent "John Doe" | Department: "Level I Support" | Role: "View only | Extended Access: Support".

![image](https://github.com/Dennimun/post-install-config/assets/146505956/4dad5adb-71d5-41fb-90f8-8937cc0fc664)


<hr>
<h3>&#9314; Agent Panel - Creating Users</h3>
Click on "Agent Panel" on the top-right of the page.

![image](https://github.com/Dennimun/post-install-config/assets/146505956/cba6a049-15e9-4dc6-9548-375ded545cf8)

Click on the "Users" tab.
Click on "Add User".
Create an Email Address and Full Name for this user (this example uses scooby@osticket.com / Scooby Doo).
Click "Add User".

![image](https://github.com/Dennimun/post-install-config/assets/146505956/d3791713-d9ff-401e-94c1-f53b9b1762c6)

![image](https://github.com/Dennimun/post-install-config/assets/146505956/2dbd9613-6236-4cee-873d-34629f451fc6)


Create another user of your choice (this example uses ken@osticket.com / Ken Ten)

![image](https://github.com/Dennimun/post-install-config/assets/146505956/aff4aab7-c13e-4e08-806c-516b3886682c)


<hr>
<h3>&#9315; Admin Panel - Configuring SLA</h3>
"SLA Plans or Service Level Agreements, are unlimited in osTicket. The purpose of the SLA Plan is to provide a length of time in which the help desk Administrator expects tickets to be closed."

Return to the "Admin Panel".
Navigate to "Manage" tab > "SLA".
Click "Add New SLA Plan".

![image](https://github.com/Dennimun/post-install-config/assets/146505956/67e3f783-c8d4-4cfd-8b66-fc3dae2a7676)


Create the following plans:
SEV-A

Grace Period: 1 hour (Amount, in hours, before tickets with this SLA will become overdue if not closed in allotted time.)
Schedule: 24/7 (Accounted for all days of the week, even on non-business days)
SEV-B

Grace Period: 4 hours
Schedule: 24/7
SEV-C

Grace Period: 8 hours
Schedule: Monday - Friday 8am - 5pm with U.S. Holidays
Click "Add Plan" for each.

![image](https://github.com/Dennimun/post-install-config/assets/146505956/710d1ccd-3d27-4e91-816d-09683c8fba0a)

![image](https://github.com/Dennimun/post-install-config/assets/146505956/ef613d93-28a9-400b-87b5-e252f54eac4c)


<hr>
<h3>&#9316; Configure Help Topics</h3>
Help Topics will help streamline your end-user’s help desk experience to ensure proper assignment and prompt response to the ticket.

Currently in the Admin Panel, navigate to "Manage" tab > "Help Topics".
Click "Add New Help Topic".

![image](https://github.com/Dennimun/post-install-config/assets/146505956/b46a9ecf-261d-4469-92b6-e9ef5115d04e)


Create Help Topics with the following names:
Business Critical Outage
Personal Computer Issues
Equipment Request
Password Reset
"Internal Notes" can be written down for personal use, but not necessary.
After that, click "Add Topic".

![image](https://github.com/Dennimun/post-install-config/assets/146505956/3f0a3ec3-f1f4-4143-8cb7-0a6c021ccd00)

![image](https://github.com/Dennimun/post-install-config/assets/146505956/36ec01fa-76a4-43c7-84fb-e1c5efec7c08)


<hr>
<h1><p align=center>All Done</p></h1

<h2><p align=center>Next Demonstration:<br><a href="https://github.com/Dennimun/ticket-lifecycle">Ticket Lifecycle Examples</a></p></h2>







