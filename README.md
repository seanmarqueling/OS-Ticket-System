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
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture28.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture29.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture30.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture31.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture32.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture33.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture34.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture35.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture36.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture37.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture38.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture39.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture40.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture41.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture42.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture43.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture44.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture45.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture46.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture47.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture48.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture49.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture50.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture51.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture52.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture53.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture54.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture55.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture56.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture57.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture58.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture59.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture60.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture61.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture62.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture63.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture64.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture65.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture66.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture67.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture68.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture69.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture70.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture71.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture72.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture73.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture74.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture75.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture76.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture77.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture78.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture79.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture80.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture81.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture82.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture83.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture84.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture85.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture86.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture87.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture88.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture89.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture90.png?raw=true)
