<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Run your VMs (virtual machines) using Azure 
- Enable IIS (Internet Information Services) 
- Install Web Platform Installer 
- Install MySQL
- Register PHP manager, and configure permnissions.
- Install HeidiSQL, configure settings and install OsTicket.


<h2>Installation Steps</h2>
</p>
<p>
 <img src="https://github.com/user-attachments/assets/51043e25-9ce1-4b73-8953-af76c1e81d30"
   </p>
  <p>
<img src="https://github.com/user-attachments/assets/7a017ee2-01cf-43fc-9e55-b697733658fb"
</p>
<p>
  
- Before we begin the installation process for OsTicket, we must first create our VM (virtual machine) using our Hypervisor (I am using Micorosoft Azure) with Windows 10 and 2 vCPUs. 
  
- Once your VM is created, please open Remote Desktop Connection on Windows and enter the IP address of the VMs.
- You will connect to your VM using the log in credentials that you created and ensure to save these credentials on a seperate notepad for future use.
</p>
<p>
<img src="https://github.com/user-attachments/assets/c0478451-cfdf-4da8-ac22-c067038e3e1a"

- We will begin the Installation process of OsTicket in your VM.
- Please copy the following URL: https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD.
- Download the file and extract the file to your Desktop as shown above.
<p>
</p>
<img src="https://github.com/user-attachments/assets/09895fc7-b872-4ffc-a4c4-7a114ae301cc" />

- We will begin to Install/Enable IIS (Internet Information Services) in Windows with CGI using the following pathway: Control Panel -> Programs -> Programs and Features -> Turn Windows on or off -> Internet Information Services -> Worldwide Web Services -> Application Development Features -> Enable file [CGI]. 
<p>
<img src="https://github.com/user-attachments/assets/7a256797-f69c-44b1-8ccd-bd61495b4f22"

- From the OsTicket Installation Files folder, install PHP manager for IIS.
(PHPManagerForIIS_V1.5.0).
</p>
<p>
<img src="https://github.com/user-attachments/assets/7655736f-ddc2-4622-8c45-cb7a836c22cb"

- After PHP Manager has been installed, Please install Rewrite Module from OsTicket Installation Files. (rewrite_amd64_en-US).
<p>
</p>
<img src="https://github.com/user-attachments/assets/37b49ba0-6647-4515-9924-a6546f1e964d" />

- Create the directory within your C drive in the file explorer C:\PHP and from osTicket-Installation-Files, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into C:\PHP.
- This will essentially extract all files from PHP 7.3.8 and aggregate them in the C:\PHP.
- Install VC_redist.x86
  <p>
   
  </p>
  <img src="https://github.com/user-attachments/assets/cfcdbc21-5ef0-4575-927e-addd424d9ef9"
- Install MYSQL 5.5.62 (mysql-5.5.62-win32).
- Typical Setup -> Launch Configuration Wizard (after install) -> Standard Configuration -> Username: root Password: root 
<p>
</p>
<img src="https://github.com/user-attachments/assets/a007f89b-de43-48de-b022-5052d5d63dfd"
 
- Open IIS as an Administrator (right click and "run as administrator")
<p>
 
</p>
<img src="https://github.com/user-attachments/assets/e4fc2f70-1345-4302-88a6-f56469b1b777"

- Register PHP from IIS (PHP Manager -> C:\PHP\php-cgi.exe)
<p>
 
</p>
<img src="https://github.com/user-attachments/assets/35ad813d-9c1c-4031-946b-33c4c4c5c70d"
 <p>
<img src="https://github.com/user-attachments/assets/ff75ddd0-ca15-49f5-b34d-08bf44707499"

- Reload IIS by doing the following (Open IIS), click "stop" and then "start" to reload the server.
- Please open "sites" and click "Browse *.80"
</p>
<img src="https://github.com/user-attachments/assets/46f1c84f-ace7-4683-9fc2-559711f4bdf5"
 </p>
<img src= "https://github.com/user-attachments/assets/0a4d986c-75fa-4617-9030-e9125b24b547"
 </p>
 
- The following extensions will have to be enabled to ensure osticket operates efficiently. 
- Have IIS open, sites -> Default -> osTicket
- Open PHP Manager
- Go to "enable or disable and extension"
- Enable: php_imap.dll
- Enable: php_intl.dll
- Enable: php_opcache.dll
</p> 
<img src="https://github.com/user-attachments/assets/6094d562-ba51-477e-a91d-99f4757f5c88"
 
- Refresh osTicket site in your browser and observe the changes.
- Initally, the the extensions that were previously disabled should be enabled now.
 </p>
<img src="https://github.com/user-attachments/assets/1f2ec870-23a9-4fc9-93c3-84e3a40bc561"
 </p>
<img src="https://github.com/user-attachments/assets/0b940a30-56d1-40b7-bdce-fa1db8b1d925"

- In this portion of the osticket installation process, please use the following directory: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
- Right click and click "rename" and rename to ost-config.php (please ensure this is accurate).
</p>
<img src="https://github.com/user-attachments/assets/ab4a28e9-857a-42a7-8b5c-0298eee7f300"

- Next we will assign permissions within ost-config.ph.
- Right click and choose "properties".
</p> 
<img src="https://github.com/user-attachments/assets/64c051b1-dfa8-4198-9ab8-ff18ddc37c03"

- Click on Security and select "Advanced" to procceed to the next prompt.
</p> 
<img src="https://github.com/user-attachments/assets/691bc79a-2274-4d22-9a88-b54140e41647"

- Disable Inheritance and rmeove all inherited permissions from the object.
</p>
<img src="https://github.com/user-attachments/assets/d516374b-552e-41d3-9635-c2c22322895c"

- Note how there are no permissions on file at this moment.
- You will add permissions by Add -> select a principal -> advanced
- You will enter Everyone in the text and click on "Check Names" and click OK.
</p>
<img src="https://github.com/user-attachments/assets/5973a0a1-9170-488f-8b47-eefe99c7ea47"

- Under Basic permissions, toggle on Full Control and click Apply.
</p>
<img src="https://github.com/user-attachments/assets/4cac4034-9e51-443b-9daf-cd10f1f51ed4"
 </p>
 
- Before proceeding to the next step of the OsTicket lab, continue setting up OsTicket in the browser.
- Revisit OsTicket localhost/osTicket/setup/install.php
- Follow the prompt and press continue to go to the next page. 

</p>
 <img src="https://github.com/user-attachments/assets/d24c9417-19f6-4778-b959-b0538c00f645"

 - Fill out System Settings and Admin User.
 - System Settings: enter "first name's Help Desk and generate any email. It does not need to be a personal one.
 - Admin User:Keep it simple  - this area will be use for frequent logging.
 - username and password example: adminuser|Password1
</p>
<img src="https://github.com/user-attachments/assets/7cbeaaf6-cace-413b-ac9d-04853f37b3d8"

- Install HeidiSQL(HeidiSQL_12.3.0.6589_Setup).
- Click next and acccept all prompts when prompted to.
</p>
<img src="https://github.com/user-attachments/assets/da3a1b6c-9d22-411e-b6a5-dfcdbb8a0ad7"

- Ensure Launch HeidiSQL is toggled on as seen in the image and select Finish.
- HeidiSQL will allow us to make a connection and create a database and configure with the program we are attempting to run(OsTicket)
- Skip the prompt that displays "check for HeidiSQL updates..."
</p>
<img src="https://github.com/user-attachments/assets/9206c373-aaf5-4845-a9e7-7fdfa742c2e2"

- Click New and provide your SQL username and password. 
- Please recall the time where you created a username and password! Friendly reminder that both username and password have "root" and select open.
</p> 
<img src="https://github.com/user-attachments/assets/611e40f6-7799-4fb9-9eda-1764073a4d39" />

- Create a new database in HeidiSQL to establish a connection with osTicket.
- Follow directory: Unnamed -> Create new database -> Name "osTicket" and select OK.
- Now that a database has been created for OsTicket, refer back to the OsTicket site.
- Once you are back in the OsTicket site OsTicket localhost/osTicket/setup/install.php, fill out the SQL Database settings.
- MySQL Database: osTicket.
- MySQL username and password: root. 
- Select Install Now.
</p>
<img src="https://github.com/user-attachments/assets/2f8df8b9-a354-4095-9a71-b0c4efb6c8b7"
</p>
<img src="https://github.com/user-attachments/assets/2d95432c-4253-40e8-a19d-659e896c3816"
 </p>
 <p>
  
 - OsTicket is finally installed! The URLs listed below in the site are admin and end-user sites for future use.
 - Go back to HeidiSQL and refresh osTicket database (right click and press refresh).
 - Observe how HeidiSQL displays all databases with a variety of information that consists of tables used by OsTicket ticket system.
 </p>
