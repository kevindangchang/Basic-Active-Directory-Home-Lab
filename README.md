# Basic-Active-Directory-Home-Lab

Set up a basic Active Directory homelab with VirtualBox. I followed along with Josh Madakor's Video Linked Below. 
https://www.youtube.com/watch?v=MHsI8hJmggI&t=963s 

Active Directory Domain Controller Lab
Overview

This lab was completed as a hands-on exercise to build a basic Windows networking environment using Windows Server, Active Directory Domain Services (AD DS), DNS, DHCP, and a Windows client machine.

I followed along with Josh's tutorial to better understand how a Domain Controller is configured and how the different services work together to create a functional Active Directory environment. The lab included configuring a Windows Server as a Domain Controller, creating an Active Directory domain, configuring networking services, and joining a Windows client to the domain.

This lab was particularly useful because I already work with Active Directory in my IT job at North Wind. While I have experience working with Active Directory in a professional environment, this lab gave me a better understanding of what is happening behind the scenes and how a Domain Controller provides authentication, DNS, DHCP, and centralized management for domain-joined computers.

Lab Objectives
Set up a Windows Server virtual machine.
Configure the server's network adapters and IP addressing.
Install Active Directory Domain Services.
Promote the Windows Server to a Domain Controller.
Create and configure an Active Directory domain.
Understand the relationship between Active Directory and DNS.
Configure DHCP for client machines.
Configure routing/NAT so clients can access the internet.
Create Organizational Units (OUs) for organizing accounts.
Use PowerShell to automatically generate Active Directory users.
Create a Windows client virtual machine.
Join the client machine to the Active Directory domain.
Log into the client using a domain account.
Environment

The lab environment consisted of virtual machines running in VirtualBox.

Domain Controller

The Windows Server virtual machine was configured with:

Hostname: DC
Role: Domain Controller
Active Directory Domain Services: Installed
DNS: Configured through Active Directory
DHCP: Configured for the internal network
Routing/NAT: Configured to allow internal clients to access the internet

The Domain Controller used separate network interfaces for the external and internal networks. The internal interface was configured with a static IP address and served as the gateway for the client network.

Active Directory Configuration

After configuring the server's networking, I installed Active Directory Domain Services (AD DS) and promoted the server to a Domain Controller.

The tutorial demonstrated creating a new forest and Active Directory domain. Once the server was promoted, I was able to access Active Directory Users and Computers (ADUC) and begin organizing the domain.

I also created Organizational Units (OUs) to separate administrative accounts from standard user accounts. This helped demonstrate how Active Directory can be structured to make managing large numbers of users and computers easier.

DNS and DHCP

One of the important concepts I gained a better understanding of during this lab was the relationship between Active Directory and DNS.

When Active Directory Domain Services was installed, DNS was also configured on the Domain Controller. The Domain Controller acts as the DNS server that domain clients use to locate and communicate with Active Directory services.

I also configured DHCP so that client machines on the internal network could automatically receive their network configuration. The DHCP configuration provided clients with information such as their IP address, default gateway, and DNS server.

The Domain Controller was also configured to provide routing/NAT, allowing machines on the internal network to communicate with the internet.

PowerShell Active Directory User Creation

One of the most useful parts of this lab was following along with Josh's PowerShell script for automatically creating Active Directory users.

Instead of manually creating hundreds of accounts through Active Directory Users and Computers, the script reads a list of names and uses PowerShell to create the accounts automatically.

The script demonstrated several useful PowerShell concepts, including:

Variables
Reading data from a text file
Converting a plaintext password into a secure password object
Creating Organizational Units
Using ForEach loops
Splitting names into first and last names
Creating Active Directory user accounts programmatically

The script was designed to generate approximately 1,000 users, demonstrating how PowerShell can automate repetitive Active Directory administration tasks.

I followed along with Josh's script and used it to generate users within my Active Directory environment. This was especially valuable because it showed me how tasks that would normally take a significant amount of time through the GUI can be automated with PowerShell.

Domain-Joined Client

After configuring the Domain Controller and creating the Active Directory users, I created a Windows client virtual machine and connected it to the internal network.

The client was configured to receive its network information from the Domain Controller through DHCP. I then joined the Windows client to the Active Directory domain and logged into the machine using a domain account.

This demonstrated one of the major advantages of Active Directory: users can authenticate against a centralized domain and use their domain credentials across computers that are joined to the same domain.

What I Learned

This lab helped me develop a much better understanding of how a Domain Controller functions within a Windows environment.

Since I already work with Active Directory at North Wind, I have experience interacting with Active Directory from the administrative side. However, this lab helped connect those day-to-day tasks to the underlying infrastructure that makes them possible.

In particular, I gained a better understanding of:

How a Windows Server becomes a Domain Controller.
How Active Directory Domain Services and DNS work together.
How clients locate and communicate with a Domain Controller.
How DHCP can automatically configure domain clients.
How a Domain Controller can provide routing/NAT for an internal network.
How Organizational Units can be used to organize Active Directory objects.
How PowerShell can automate Active Directory administration.
How domain users authenticate to domain-joined computers.
Connection to My IT Experience

I found this lab especially relevant to my current IT work at North Wind, where I already work with Active Directory.

Following the tutorial allowed me to go beyond simply using Active Directory and gave me a better understanding of how the Domain Controller and its supporting services are configured and interact with one another.

The PowerShell portion was also particularly useful because it demonstrated how automation can be used to manage Active Directory at scale. Rather than manually creating individual accounts, administrators can use scripts to create and configure large numbers of users efficiently.

Overall, this lab helped strengthen my existing Active Directory knowledge while giving me more hands-on experience with Windows Server administration, Domain Controllers, networking, DNS, DHCP, and PowerShell automation.
