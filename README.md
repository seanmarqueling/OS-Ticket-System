# OS-Ticket-System
How to setup os Ticketing System

os Ticket Software Setup overview:
- Setup a Virtual Machine in Azure
- Install the osTicket requirements
- Install osTicket itself
- Do the after-installation configuration of osTicket

## Instruction - Setup Azure Network

From the home screen of Azure, either select Virtual Machine or enter it in the search bar on top.

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/1.png?raw=true)

Click on create a VM.

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/2.png?raw=true)

- Resource Group - osTIcket
- Virtual Machine Name: osticket-vm
- image: Windows10 Pro, version 22H2 - x64 Gen2

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture3.png?raw=true)

- Size: Standard_D2s_v3 - 2vcpus,8 GiB memory
- username: labuser
- Password: osTicketPassword1
- Click on Review + Create
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/99.png?raw=true)

Copy the Public IP Address for the VM. We are going to use RDP to get into the VM.

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture4.png?raw=true)

Once in the VM, open up Microsoft Edge and use the following link to download 
[osTicket](https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD)

After the file is downloaded, unzip it and put the folder on the desktop and name it 'os Ticket-Installation-Files'.

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture5.png?raw=true)

Now we have to make some changes to the VM - go in the control panel and click on Uninstall a program.

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture7.png?raw=true)

Click on Turn Windows Features on or off.

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture8.png?raw=true)

We need to turn on a couple of features before we install the os Ticketing System.
- Click on 'Internet Information Services'
- Click on 'World Wide Web Services'
- Click on Application Development Features'
- Select 'CGI'

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture9.png?raw=true)

Open up the osTicket-Installation-Files - we will now install PHPManager & rewrite_amd64.

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture10.png?raw=true)

Install PHP and rewrite - say yes and click continue/finish.

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture11.png?raw=true)

We will now need to create a new directory in the C Drive.
- Open up Windows Explorer

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture12.png?raw=true)

Create a foilder in the C drive and call in PHP.

We will unzip PHP7.3.8(php-738-nts-Win32-VC15x86.zip)

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture13.png?raw=true)

Next we need to install VC_redist.x86 - click on install and move on.

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture14.png?raw=true)

Now we need to install mysql-5.5.62-win32

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture15.png?raw=true)

Select Typical Setup and then select Standard Configuration.

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture16.png?raw=true)

Click next

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture17.png?raw=true)

For our osticket admin login information:
- user: adminuser
- password: root

In the setup:
- New root password: root
- Confirm: root
- Click next / continue until the end
- (Note, for the sake of a lab we are using these as passwords - do not use them in real settings)

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture18.png?raw=true)

Now in order to use the files that we installed we need to look up IIS (Internet Information Service Manager) in Windows.

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture19.png?raw=true)

When that opens, select PHP Manager.

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture20.png?raw=true)

- Click on Register new PHP Version
- Click on the 3 dots
- Look up PHP folder on the C Drive
- Select php-cgi

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture21.png?raw=true)

- Click on the left side bar - osticket-vm (osticket-vm\lab)
- On the right side bar click on Stop
- Click on Start (this will restart the server)

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture22.png?raw=true)

Go back to osTicket-Installation-Files folder. We are going to unzip osTIcket-v1.15.8.

Extract the folder into osTicket-Installation-Files folder.

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture23.png?raw=true)

Copy and paste the upload folder to C -> inetpub -> wwwroot

Rename upload to osTicket

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture24.png?raw=true)

After renaming the file, go back to the IIS and restart the server by clicking on stop and then start.

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture25.png?raw=true)

Now are going to open up the Installer for osTicket.

In the IIS:
- Click on Sites
- Click on Default Web Site
- Click on osTicket
- On the right side bar - click on Browse *:80 (http)

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture26.png?raw=true)

We are now looking at the the Installer for osTicket.

On this screen we can see that there are a number of extensions that are not enabled.

We will ned to go back in IIS to enable them.

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture27.png?raw=true)

- Go in the IIS and on the left hand side
- Click on osTIcket
- Click on PHP Manager

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture28.png?raw=true)

- Click on enable or disable an extension

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture29.png?raw=true)

We want to enable the following (right-click on each item and select enable):
- php_imap.dll
- php_intl.dll
- php_opcache.dll

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture30.png?raw=true)

Refresh the browser to make sure those extensions are now enabled.

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture31.png?raw=true)

Now go back to Windows Explorer and go to the following directory:
- Windows(C:)/inetpub/wwwroot/osTicket/include
- Locate a file called ost-sampleconfig.php
- Rename the file to ost-config.php

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture32.png?raw=true)

- Right click ost-config.php
- Select Properties
- Click on System
- Select Advanced

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture33.png?raw=true)

- Click on Disable inheritance

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture34.png?raw=true)

- Select Remove all inherited permissions from this project

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture35.png?raw=true)

- Click on Add
- for Principal leave it as Select a principal
- In Enter the object name to select - type in Everyone
- Click on Check Names
- Click on OK

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture36.png?raw=true)

- Click on Full Control
- Click Ok to Everything

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture37.png?raw=true)

We are going to continue setup after enabling the extensions - click on Continue

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture38.png?raw=true)

The following fields need to be filled out (Username and Password are the most important:
- Helpdesk Name: Sean's Help Desk
- Default Email: sean.m.it@gmail.com
- First Name: Sean
- Last Name: Marqueling
- Email Address: me@seanmit.com
- Username: adminuser
- Password: Password1

Before we finish and click on  install, we need to install HeidiSQL

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture39.png?raw=true)

Go back to osTicket-Installation-Files and open up HeidiSQL_12.3.06589_Setup

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture40.png?raw=true)

- Click on I accept the agreement
- Click on next all the way through
- Click on Install
- Click on Finsh

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture41.png?raw=true)

We do not need to download and isntall build 7066 - click on skip.

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture42.png?raw=true)

With HeidiSQL open:
- Click on New
- User: root
- Password: root
- Click on Open

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture43.png?raw=true)

- Right click on Unnamed
- Select Create New
- Select Database

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture44.png?raw=true)

- Name: osTicket
- Click on OK

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture45.png?raw=true)

Go back to osTIcket Installation and enter in the following:
- Database: osTicket
- username: root
- password: root
- Select Install Now

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture46.png?raw=true)

Go back to HeidiSQL Database information
- Right click on osTIcket
- Click on Refresh
We should now see the information for the osTicket Database populate on the right side.

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture47.png?raw=true)


Here is the login page link.
[osTicket Login](http://localhost/osTicket/scp/login.php)
- Username: adminuser
- Password: Password1

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture48.png?raw=true)

This is the first page for the ticketing system.

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture49.png?raw=true)

[End User Portal](https://localhost/osTicket)
This page is for the end users to submit their tickets for IT.

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture50.png?raw=true)

Now that the software is installed - we need to do some post installation setup for osTicket.

## Instructions - Setup up osTicket with roles, rules, teams, SLAs

We need to make sure we are on the admin page, to do this we need to click in the upper right hand corner if it says Admin Panel. This will take us to the admin page. However, if it says Agent Panel in the upper right hand corner, we are already on the admin page.

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture51.png?raw=true)

- Click on Roles

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture52.png?raw=true)

- Click on Add New Role

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture53.png?raw=true)

We will call this new role 'Supreme Admin'

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture54.png?raw=true)

After naming the role
- Click on Permissions
- Check Everything
- Click on Tasks

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture55.png?raw=true)

- Select everything on tasks
- Click on Add Role

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture56.png?raw=true)

Supreme Admin rols is now created.

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture57.png?raw=true)

Now we are going to create a new agent.
- Click on Agents
- Click on Departments
- Click Add New Department

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture58.png?raw=true)

- Parent: Top-Level Department
- Name: SysAdmins
- Click on create

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture59.png?raw=true)

SysAdmins role is now created.

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture60.png?raw=true)

Now we are going to add teams.
- Click on Agents
- Click on Teams
- Click on Add New Team

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture61.png?raw=true)

We will call the team:
- Name: Online Banking
- Team Lead: Josh Cypress (we will have to add his information during this process)
- Click on Members

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture62.png?raw=true)

Josh Cypress does not exist in the system, we need to add their agent information:
- Name: Josh
- Last Name: Cypress
- Email: JCypress999999999@gmail.com
- Department: Support
- Primary Role: Supreme Admin
- Password: Labuser123
- Click on Create

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture63.png?raw=true)

After that is created:
- Click on Agents
- Click on Members
- Enter in your Name
- Click on Create Team

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture64.png?raw=true)

Online banking team is now created.

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture65.png?raw=true)

We now need to create a setting to allow Users to create tickets on osTicket without requiring an account:
- Click on settings
- Click on Users
- Click on Settings
- Leave all the fields as they are and make sure Require registration and login to create tickets is not checked.
- Save Changes

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture66.png?raw=true)

We are now goign to add two agents named Jane Doe and John Doe to the system:
- Click on Agents
- Click on Agents
- Select Add New Agent

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture67.png?raw=true)

- NameL Jane Doe
- Email Address: JDoe999999999@gmail.com
- Username: Jane
- Click on Set Password

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture68.png?raw=true)

- Uncheck Send the agent a password reset email
- Passowrd: Password1
- Do not check Require password change at next login
- Select Update

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture69.png?raw=true)

Go to Access:
- Primary Department: SysAdmins
- Role: Supreme Admin

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture70.png?raw=true)

Go to Teams:
- Team: Online Banking
- Click Create

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture71.png?raw=true)

- NameL John Doe
- Email Address: JnDoe999999999@gmail.com
- Username: John
- Click on Set Password

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture72.png?raw=true)

- Uncheck Send the agent a password reset email
- Passowrd: Password1
- Do not check Require password change at next login
- Select Update
  
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture73.png?raw=true)

Go to Access:
- Primary Department: Support
- Role: View Only

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture74.png?raw=true)

Both agents are now created.

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture75.png?raw=true)

Next we are going to go into the Agent Panel and create a new End User.
- Click on Agent Panel on the top right.

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture76.png?raw=true)

- Go to Users
- Click on Add User

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture77.png?raw=true)

- Email Address: kathy999999999@gmail.com
- Full Name: Kathy Bates
- Click on Add User

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture78.png?raw=true)

Last part of the setup, we will now add SLA's (Service Level Agreements) for our ticketing system.

- Go back into the Admin Panel

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture79.png?raw=true)

- Click on Manage
- Click on SLA
- Click on Add New SLA Plan

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture80.png?raw=true)

Name: Sev-A
Grace Period: 1
Schedule: 24/7
Click on Add Plan

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture81.png?raw=true)

- Click on Add New SLA Plan
- Name: Sev-B
- Grace Period: 4
- Schedule: 24/7
- Click on Add Plan


![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture82.png?raw=true)

- Click on Add New SLA Plan
- Name: Sev-C
- Grace Period: 8
- Schedule: Monday - Friday 8am - 5pm with U.S. Holidays
- Click on Add Plan

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture83.png?raw=true)

After the SLA's are created we need to create the Help Topic for them:
- Click on Manage
- Click on Help Topics
- Click on Add New Help Topic

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture84.png?raw=true)

- Topic: Business Critical Outage
- Parent Topic: Report a Problem
- Click on Add Topic

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture85.png?raw=true)

- Click on Add New Help Topic
- Topic: Personal Computer Issues
- Parent Topic: Report a Problem
- Click on Add Topic

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture86.png?raw=true)

- Click on Add New Help Topic
- Topic: Equipment Request
- Parent Topic: General Inquiry
- Click on Add Topic

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture87.png?raw=true)

- Click on Add New Help Topic
- Topic: Password Reset
- Parent Topic: Report a Problem
- Click on Add Topic

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture88.png?raw=true)

- Click on Add New Help Topic
- Topic: Other
- Parent Topic: General Inquiry
- Click on Add Topic

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture89.png?raw=true)

Here are all of the Help Topics that were created.

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture90.png?raw=true)
