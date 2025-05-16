<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Create Resource Group
- Create Virtual Network and Subnet
- Create Domain Controller and Client VMs
- Configure all VMs using PowerShell

<h2>Deployment and Configuration Steps</h2>

<p> Domain Controller's Setup and Configuration

1. Create the Domain Controller VM (Windows Server 2022) named “DC-1”
![image](https://github.com/user-attachments/assets/2fa9cc97-e4b0-43db-85b8-1dbc9c735a03)

2. After the VM is created, set the Domain Controller’s NIC Private IP address to be static
![image](https://github.com/user-attachments/assets/9942a32c-6d2a-4e0e-94bf-8a4a50fcd9b0)

3. Log in to the VM and disable the Windows Firewall (for testing connectivity)

</p>
<br />

<p> Client's Setup and Configuration
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
1. Create the Client VM (Windows 10) named “Client-1”

   ![image](https://github.com/user-attachments/assets/e1f2ea02-b140-4e08-a1f0-03735f7cea16)

2. Attach it to the same region and Virtual Network as DC-1
   
   ![image](https://github.com/user-attachments/assets/3b8e82d0-ee07-4f45-bb54-78781eba3453)

4. After VM is created, set Client-1’s DNS settings to DC-1’s Private IP address
   
![image](https://github.com/user-attachments/assets/830b8eb8-2d0a-4842-af99-847ee2ebf347)

6. From the Azure Portal, restart Client-1

7. Log in to Client-1
   
8. Attempt to ping DC-1’s private IP address
   
![image](https://github.com/user-attachments/assets/5222b331-0086-4fb0-a428-9c998fc45f5e)

10. Ensure the ping succeeded


11. From Client-1, open PowerShell and run ipconfig /all
![image](https://github.com/user-attachments/assets/1a694c62-4d61-4b96-a8aa-bcfc22124722)

12. The output for the DNS settings should show DC-1’s private IP Address

</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
</p> 
</p>
<br />
