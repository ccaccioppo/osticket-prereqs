# osticket-prereqs
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial covers the requirements and installation process for the open-source help desk ticketing system, osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Ticket Lifecycle Stages</h2>

- Intake
- Assignment and Communication
- Working the Issue
- Resolution

<h2>Lifecycle Stages</h2>

<p>
<img src="https://i.imgur.com/Iu8EC4s.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
We start by creating a resource group in Microsft Azure and name it osTicket. Then create a virtual machine within the resource group. Next we select Windows 10 pro for the image of the VM, making sure it has a least 2 vCPUs. The VM will serve as a practice space. 
</p>
<br />

<p>
<img src="https://i.imgur.com/H2B3g7x.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, access the VM via Remote Desktop Protocol (RDP). Copy the Public IPv4 address listed in the Azure portal for the VM and use it to establish the RDP connection.
</p>
<br />

<p>
<img src="https://i.imgur.com/2VqhhFo.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After connecting to the VM, enable IIS by opening the Control Panel and going to Turn Windows Features On or Off. Scroll down to find Internet Information Services (IIS), then check the box to enable it.
</p>
<br />
</p>
<br />

<p>
<img src="https://i.imgur.com/jdy6kVT" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, download all the required files using the provided link to install and set up osTicket. Then, from the osTicket Installation folder, find and install PHP Manager to continue with the installation process.  

  Link: https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD
</p>
<br />

<p>
<img src="https://i.imgur.com/BraQ2Sp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Within the same folder, install the Rewrite Module to continue configuring the environment.
</p>
<br />

<p>
<img src="https://i.imgur.com/3G7QEou.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/BJ7pQXn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create the directory C:\PHP. Unzip the file PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and extract all its contents into the C:\PHP directory.
</p>
<br />

<p>
<img src="https://i.imgur.com/vnapOUJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Install VC_redist.x86.exe from the osTicket Installation folder to ensure the necessary Visual C++ Redistributable components are in place.
</p>
<br />

<p>
<img src="https://i.imgur.com/6Ni4PkJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Install MySQL 5.5.62 (mysql-5.5.62-win32.msi) from the osTicket Installation folder to set up the MySQL database server.
</p>
<br />

<p>
<img src="https://i.imgur.com/HFBKqHa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open IIS Manager as an administrator. Register PHP within IIS by configuring the necessary settings. Afterward, restart the server by selecting Restart in the IIS Manager.
</p>
<br />

<p>
<img src="https://i.imgur.com/dUEDOI2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the osTicket-Installation-Files folder, unzip osTicket-v1.15.8.zip and copy the upload folder to C:\inetpub\wwwroot. Then, within C:\inetpub\wwwroot, rename the upload folder to osTicket.
</p>
<br />

<p>
<img src="https://i.imgur.com/ofoOo0Z.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go back to IIS Manager and restart the server. To enable the required PHP extensions, go to Sites > Default > osTicket, then double-click on PHP Manager. Choose the option "Disable or enable an extension" and enable the extensions php_intl.dll, php_opcache.dll, and php_imap.dll. Once done, refresh the osTicket web server and confirm that the Intl Extension is now active.
</p>
<br />

<p>
<img src="https://i.imgur.com/JEdBG6b.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Navigate to C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php and rename the file to ost-config.php in the same directory (C:\inetpub\wwwroot\osTicket\include).
</p>
<br />

<p>
<img src="https://i.imgur.com/vFIs9DL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Assign the appropriate permissions to ost-config.php by right-clicking the file and selecting Properties. In the Security tab, disable inheritance, remove all existing permissions, and grant Everyone full access.
</p>
<br />

<p>
<img src="https://i.imgur.com/HZnNtf2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Finally, continue the osTicket setup in your browser by clicking Continue. Assign a name to your helpdesk according to your preference, and choose a default email address to receive notifications for customer-submitted tickets. Congratulations, your setup is complete!
</p>
<br />
