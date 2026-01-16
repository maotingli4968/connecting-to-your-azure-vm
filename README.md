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


<p>
  <img width="750" height="472" alt="image" src="https://github.com/user-attachments/assets/1b5fb206-f4c5-4516-8608-667efb0404e1" />
</p>

<p>
  <img width="750" height="472" alt="image" src="https://github.com/user-attachments/assets/275b0626-8fb2-40e8-a8b5-4dde2b2b60cd" />
</p>

<p>
  <img width="750" height="472" alt="image" src="https://github.com/user-attachments/assets/40a91d78-8a82-4972-a352-97b742a9dafa" />
</p>


- Create Windows Virtual Machine (Networking Tab)
    - On the networking page of the Windows VM creation process, Azure will automatically create a virtual network for you.
    - Instead of using the default, click Create new and name it something like windows-VNet.
    - Keep the rest of the settings as default for now.
    - This will ensure that your Windows VM is connected to its own dedicated network
 
  <p align="center">
  <img src="https://github.com/user-attachments/assets/4faec529-175e-4856-b903-32fc96be013e" alt="image" width="900" />
</p>

<br/>

<p align="center">
  <img src="https://github.com/user-attachments/assets/dc053dd9-02c5-44fd-9b78-e9314a6f345a" alt="image" width="900" />
</p>

<br/>

<p align="center">
  <img src="https://github.com/user-attachments/assets/addf4431-6488-458b-bacc-0731868fcf87" alt="image" width="900" />
</p>

<br/>

<p align="center">
  <img src="https://github.com/user-attachments/assets/4e621ced-a3cc-463f-a34b-fe6dc4a11df5" alt="image" width="900" />
</p>


- Create Linux Virtual Machine (Basics Tab)
    - Now, repeat the process to create a second VM, this time for Linux.
    -  Name it Linux-VM, select the same Resource Group, and choose an image such as Ubuntu Server 22.04.
    -  Set the username and password fields, using the same credentials as the Windows VM to make it easier to log in later.
    -   Make sure to keep the region the same as your first VM (East US 2), otherwise you may run into issues attaching it to the same network

  <p align="center">
  <<img width="975" height="610" alt="image" src="https://github.com/user-attachments/assets/39238aa7-545f-4a84-b9d2-064c6d6afb6f" />
</p>


- Create Linux Virtual Machine (Networking Tab)
    - On the Linux VM networking page, don’t create a new network.
    - Instead, select the previously created windows-VNet and the default subnet.
    - If the option doesn’t appear right away, refresh the page and try again — this sometimes happens due to portal delays.
    - Once selected, click Review + Create to finalize the VM

  <p align="center">
  <img src="https://github.com/user-attachments/assets/25db575a-5e5d-4d8d-9e22-a858aca043a9"
       alt="image"
       width="700" />
</p>


-  Resource Group Overview
    - Once both VMs are deployed, go to your Resource Group overview page. You’ll see that several items have been created automatically:
    -  Both VMs (Windows-VM and Linux-VM)
    -  	A Virtual Network (Lab2-VNet)
    -  	Public IP addresses
    -  	A Network Security Group
    -  	Disks and network interfaces
This overview page helps confirm that all your resources are tied together correctly under the same Resource Group

<p align="center">
  <img src="https://github.com/user-attachments/assets/25db575a-5e5d-4d8d-9e22-a858aca043a9"
       alt="image"
       width="700" />
</p>

- Networking Verification
    - To confirm networking, open each VM and scroll down to view its Networking settings.
    - Check that both Windows-VM and Linux-VM are connected to the windows-VNet  and are assigned to the default subnet.
    - This ensures that the two VMs are on the same virtual network and can communicate with each other

- Windows-VM
 <p align="center">
  <img src="https://github.com/user-attachments/assets/1443bf71-94e7-4431-aa58-c97afb2492c6"
       alt="image"
       width="700" />
</p>

- Linux-VM 
<p align="center">
  <img src="https://github.com/user-attachments/assets/961d1490-bc75-4a4d-ad6d-6f8c3bfb5b9a"
       alt="image"
       width="700" />
</p>


- Remote Desktop Connection Client
    - On your local computer, open the Remote Desktop client.
    - In Windows, press Win + R, type mstsc, and press Enter.
    - Copy the Public IP address of your Windows-VM from the Azure Portal and paste it into the Remote Desktop Connection window.
    - Click Connect
 
<p align="center">
  <img src="https://github.com/user-attachments/assets/e7eb5727-b115-4634-a739-057c3980e238"
       alt="image"
       width="700" />
</p>

<br/>

<p align="center">
  <img src="https://github.com/user-attachments/assets/c33f62c0-9654-4d65-be53-8d496435d37d"
       alt="image"
       width="700" />
</p>

- Remote Desktop Login Prompt
    - When prompted, enter the username and password you created earlier.
    -  If a certificate warning appears, accept it to proceed.
    -  This step logs you into the Windows VM using Remote Desktop.
 
 <p align="center">
  <img src="https://github.com/user-attachments/assets/63a639f0-d776-4719-b57a-05a16cb61940"
       alt="image"
       width="700" />
</p>





  








</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
