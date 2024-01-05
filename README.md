<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
In this lab, we will outline the prerequisites and installation of a popular and open-source help desk ticketing system called osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)
- MySQL

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- [osTicket Installation Files](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) 
- Heidi SQL

<h2>Installation Steps</h2>


<p>
First, open Azure Portal, and create a resource group titled "osTicket". After that create a virtual machine equipped with Windows 10. Then you are going to remote desktop to the VM's public IP address.
</p>
<br />

<p>
Now that you're connected to your VM you will have to enable Internet Information Systems(IIS). IIS is a web server that allows the VM's computer to serve up websites like osTicket. Access the control panel and then select the option "uninstall a program". From the left select "Turn Windows features on or off". A list will pop up and then you will enable Internet Information Services. After that expand on IIS, click on World Wide Web Services-->Application Dev Features-->Check CGI box-->OK.
</p>
<p>
<img src="https://i.imgur.com/CbwfX0A.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
Next, from the Installation Files download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) and the Rewrite Module (rewrite_amd64_en-US.msi). 
</p>

<p>
<img src="https://i.imgur.com/th1QTiq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
After that, you need to create a PHP directory in the C: drive. From the Installation Files download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP.
</p>
<p>
<img src="https://i.imgur.com/MIB0vMD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
<img src="https://i.imgur.com/C2dw437.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
Then from the Installation Files, download and install VC_redist.x86.exe. Install MySQL 5.5.62 (mysql-5.5.62-win32.msi), MySQL is a database that osTicket relies on.  
</p>
<p>
<img src="https://i.imgur.com/M3C8Een.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
<img src="https://i.imgur.com/Vw9dkdG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
Now you need to open IIS as an Administrator. Go to the start menu and type IIS, right-click on IIS, and click "Run as administrator". 
</p>
<p>
<img src="https://i.imgur.com/tSMyqRh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
Register PHP from within IIS. Then you need to reload IIS (Open IIS and Stop and Start the server). 
</p>
<p>
<img src="https://i.imgur.com/CE9jRe1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
<img src="https://i.imgur.com/jENoPV0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
<img src="https://i.imgur.com/xEACeIn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
From the Installation Files, download osTicket v1.15.8. After that extract and copy "upload" folder to c:\inetpub\wwwroot. Within c:\inetpub\wwwroot, rename "upload" to "osTicket". Then you need to reload IIS (Open IIS and Stop and Start the server). 
</p>
<p>
<img src="https://i.imgur.com/78CkHVT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
<img src="https://i.imgur.com/H5jupzl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
Go to Sites, click on Default, and then osTicket. On the right click “Browse *:80”. An osTicket Installer page will pop up. 
</p>
<p>
<img src="https://i.imgur.com/GMT4HiB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
<img src="https://i.imgur.com/DNnlS7J.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
now you need to return to IIS, click on Sites, then Default, and then osTicket. Double-click on PHP Manager and then click on "Enable or disable an extension". Enable: php_imap.dll, php_intl.dll and php_opcache.dll. Refresh the osTicket site in the browser and observe the changes. 
</p>
<p>
<img src="https://i.imgur.com/RdKimo9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
<img src="https://i.imgur.com/pXxtHtF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
<img src="https://i.imgur.com/KHJgoJO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
Now the next step is to rename ost-config.php. You will change C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php to C:\inetpub\wwwroot\osTicket\include\ost-config.php. You will also need to assign permissions to ost-config.php. Click on Disable Inheritance, then Remove All. And then add New Permissions, click on Everyone, then Full Control. 
</p>
<p>
<img src="https://i.imgur.com/of7zvcb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
<img src="https://i.imgur.com/A510mEL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
Now continue setting up osTicket in the browser.
</p>
<br />
<p>
From the Installation Files, download and install HeidiSQL. Open HeidiSQL, create a new session, and then connect to the session using the username and password when you set up MySQL. Next you will create a database called "osTicket". 
</p>
<p>
<img src="https://i.imgur.com/q5ChlVE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<br />
<p>
osTicket should be installed. Next step is to clean up. Delete: C:\inetpub\wwwroot\osTicket\setup. Then set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php.
</p>
<p>
<img src="https://i.imgur.com/F4kRIVR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
Now you can browse to your help desk login page: http://localhost/osTicket/scp/login.php. The osTicket installation is done!
</p>
<p>
<img src="https://imgur.com/x9ga2kj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://imgur.com/MRl1dL0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
