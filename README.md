<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure Subscription/Resource group (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites </h2>
- Follow this <a href="https://drive.google.com/drive/u/2/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">link</a> and download all available files into Windows 10 Virtual Machine.       </p> - Enable IIS in Windows, along with Management controls

 
<h2>Installation Steps</h2>

<p>
<img src="[https://i.imgur.com/DJmEXEB.png](https://imgur.com/kBEEeyB)" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Before beginning your adventure into OsTicket, it is required first to develop your environment. Start a new Microsoft Azure subscription or log into a pre-existing account. Create a resource group when subscription is made and set up a Virtual Machine (Named OsTicket-VM) with Windows 10, 2-4 CPUs, with a new VNET with installation. Use Remote Desktop Connection, include the Public IP address and user login from the resource group for the aforementioned Virtual Machine in order to gain access. 
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After accessing the VM, open the Control panel via search. Use this path to and enable CGI and Common HTTP Features. World Wide Web services --> Application Development Features --> CGI and Common HTTP Features. Do not forget to also enable IIS Management Console through: Internet Information Services --> Web Management Tools --> IIS Management Console.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Install PHP Manager, Rewrite Module, and PHP 7.3.8. Create a directory titled "C:\PHP", unzip contents of PHP into directory.  Install VC Redist and MySQL (Typical setup/Standard Config). Open IIS as an admin and register PHP within IIS. Reload IIS, install osTicket from the installation folder, extract and copy "Upload" folder into c:\inetpub\wwwroot, and rename "Upload" to "osTicket" 
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Reload IIS and on the left panel, access Sites --> Default --> osTicket. On the right panel, click "Browse*:80". You will be prompted to the osTicket website, note some extensions are not available. Use the same path as before to reach osTicket in IIS and double click PHP Manager. Enable php_imap.dll, php_intl.dll, and php_opcache.dll. Refresh osTicket website and make sure all three extensions have been implemented. In your files, go to C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php and rename "ost-sampleconfig.php" to "ost-config.php". Access permission on ost-config.php, disable inheritance/remove all, and add full permissions for "Everyone". 

<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Back in the osTicket Browser, hit continue and fill in your information up until the MySql section. Download HeidiSQL, create a new session (root/Password1), and create a new database called osTicket within this session. Fill out MySQL section with database name (osTicket), username (root), and password that was just created. osTicket has finally been created and is ready for Post-install configuration!
<br />
