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

![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture5.png?raw=true)



![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture7.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture8.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture9.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture10.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture11.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture12.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture13.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture14.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture15.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture16.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture17.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture18.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture19.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture20.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture21.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture22.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture23.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture24.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture25.png?raw=true)
![image](https://github.com/seanmarqueling/OS-Ticket-System/blob/main/Picture26.png?raw=true)
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
