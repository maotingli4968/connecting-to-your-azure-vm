<p align="center">
<img src="https://www.devopsschool.com/blog/wp-content/uploads/2021/10/microsoft-azure-virtual-machines.jpg"/>
</p>

<h1>Remote Desktop – Connecting to Your Azure Virtual Machine</h1>
This tutorial outlines the steps of how to use Remote Desktop to connect to azure virtual machine.<br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines)
- Remote Desktop Protocol (RDP)
- Windows 11
- Ubuntu Linux Server (22.04 LTS)

<h2>Operating Systems Used </h2>

- Windows 11 (Host Machine & Remote VM)
- Ubuntu Linux 

<h2>List of Prerequisites</h2>

- Active Azure subscription:
  see a step-by-guide on how to create a free azure subscription: https://www.geeksforgeeks.org/devops/how-to-create-a-free-azure-account/
- A Resource Group containing:
  1. One Windows 11 Virtual Machine (VM)
  2. One Linux (Ubuntu) Virtual Machine
  3. A Virtual Network (VNet) with a Subnet
  4. A Network Security Group (NSG) automatically created during VM setup
  
- Saved VM credentials (username/password created during setup)


<h2>Installation Steps</h2>


- Create Resource Group
  - Log in to the Azure Portal.
  - Create a new Resource Group (e.g., `RG-Network-Activities`).
  - Select the correct region (e.g., Canada Central).
  - Click Review + Create, then Create.
  - This Resource Group will hold all resources built in this lab.


<p>
  <img width="975" height="904" alt="image" src="https://github.com/user-attachments/assets/a5c26e75-4e30-400f-915d-122a845e649a" />
</p>
<p>

  
- Create Windows Virtual Machine (Basics Tab)
  -  Next, search for Virtual Machines in the Azure Portal and click Create Virtual Machine.
  -  Select the Resource Group you just created.
  -  Give the VM a name like Windows-VM and choose Windows 10 Pro as the image. Make sure you scroll down to confirm the licensing checkbox — this is often forgotten.
  -  For authentication, create a username (for example, labuser) and a password you will remember . Note these down since you’ll need them later. 
</p>
<br />

<p>
<img width="975" height="712" alt="image" src="https://github.com/user-attachments/assets/1b5fb206-f4c5-4516-8608-667efb0404e1" />
>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
