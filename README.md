# osticket-prereqs
<p align="center">
<img src= "https://i.imgur.com/PA3zADM.png"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
In this tutorial we will go through the full installation for osTicket and the prerequisites required to meet installation. I will install osTicket on an Azure VM(Virtual Machine). This tutorial will assume you have a VM ready and are logged into it using remote desktop connection. If you have not created a VM do that before continuing onto next step. To get started click here for <a href="https://drive.google.com/drive/u/2/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">INSTALLATION FILES!</a>

<h2>
<p>
<img src= "https://i.imgur.com/GlMff8v.png"/>
</p>
 <h/2>

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)
- MySQL

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Installation Steps</h2>
<h2>First to install/enable IIS Go to Control Panel > Programs > Turn Windows Features On or OFF > Click and Expand Internet Information Services > click and expand Web Managment Tools > Check IIS Managment Console > Click and expand World Wide Web Services > Click and expand Application Development Features > Check CGI > Click OK<h2/>
<p>

</p>
<br />

<p>
<img src="https://i.imgur.com/0heoYEy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<h>Next Download/Install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) from INSTALLATION FILES<h2/>
</p>
<br />

<p>
<img src="https://i.imgur.com/4lQoWJ5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next Download/Install Rewrite Module (rewrite_amd64_en-US.msi) from INSTALLATION FILES
</p>
<br />
<p>
<img src="https://i.imgur.com/rEOJqkY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next Create the directory C:\PHP 
 <P>Open File Explorer > This PC > Windows (C:) Drive > Right Click to add NEW FOLDER > name it "PHP"</P>
</p>
<br />

<p>
<img src="https://i.imgur.com/f9VwzAH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into C:\PHP From the installation files
</p>
 <p> Double-click on PHP-7.3.8 > Right Click to EXTRACT ALL > Click BROWSE > This PC > Windows (C:)> Click PHP > EXTRACT</p>
<br />
<p>
<img src="https://i.imgur.com/FEmn7wh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
 <img src="https://i.imgur.com/Rk2nAjp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<img src="https://i.imgur.com/oC4HYF8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next Download/Install VC_redist.x86.exe. from the INSTALLATION FILES
</p>
<P> Double-click and Install</P>
<br />
<p>
<img src="https://i.imgur.com/4W1slB9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next Dowload/Install MySQL 5.5.62 (mysql-5.5.62-win32.msi)

<P> Double-click > Click I "agree" > Select TYPICAL > INSTALL </P>
<P> Launch Configuration Wizard (after install) </P>
 <p> Select STANDARD CONFIGURATION > Select INSTALL AS WINDOWS SERVICE (make sure "Launch my sql server..."is checked) > Root will be your username create a password. example: </p>
 <p>Username: ROOT</p>
 <p>Password: Password1 </p>
 
 
<img src="https://i.imgur.com/Z2UPFwz.png"/>
<img src="https://i.imgur.com/aKCqWMI.png"/>
<img src="https://i.imgur.com/Nr1r1pJ.png"/>
</p>
<p>
Next Open IIS as an Admin, register PHP, then restart the server.</p>
<p> Type IIS in start menu > Click on RUN AS ADMINISTRATOR > Select PHP MANAGER > Select Register new PHP Version > Click BROWSE > Select PHP CGI (make sure php executable) > ok > Click RESTART </p>
<p>
<img src="https://i.imgur.com/pimEJ53.png"/>
<img src="https://i.imgur.com/Tp47Hk5.png"/>
<img src="https://i.imgur.com/2a5ZQ5X.png"/>
<img src="https://i.imgur.com/eDhTKa2.png"/>
<img src="https://i.imgur.com/Npu1Q9r.png"/>
</p>
<p> Next Install osTicket v1.15.8 and Drag the "UPLOAD" folder into wwwroot folder and right click to rename "UPLOAD" folder to "osTicket" </p>
<img src="https://i.imgur.com/d8cTobw.png"/>
<img src="https://i.imgur.com/r6eVgAB.png"/>
 <P> Next open IIS > click RESTART > Sites > Default > osTicket (Double-click) > Browse 80* </p>
 <img src="https://i.imgur.com/RI1sFNo.png"/>
<p> you should make it to the osTicket webpage; if so, you did it correctly. If not check all your steps or restart the tutorial. </P>
<p> NOTE: some php extensions are disabled (with red X) to enable php extensions go back to IIS > Sites > Default Web Site > osTicket > php manager (double-click)> Click on PHP extensions. Scroll down list to find: </p>
<p>Php_imap.dil</p>
<p>Php_intl.dil</p> 
<p>Php_opache.dil</p>
<p>click enable extensions and Restart the server</p>
<img src="https://i.imgur.com/xlDb0QQ.png"/>
<img src="https://i.imgur.com/3up7CXo.png"/>
<p> Before you continue on osTicket go back to the Downloads folder and INSTALL HeidiSQL</p>
<img src="https://i.imgur.com/RJs8RZ6.png"/>
<p> After installing, HeidiSQL will launch.
<h2>Click NEW > Enter password we created earlier for mysql (example: Password1) > Click OPEN<h2/></p>
<img src="https://i.imgur.com/DMHSshw.png"/>
<h2>Right Click on UNNAMED > Create New > Database (name it osTicket) > Click Ok<h2/>
<img src="https://i.imgur.com/plHNmKg.png"/>
</p>
<p> Next rename ost-sampleconfig.php to ost-config.php </p>
<p> WINDOWS (C:) DRIVE > inetpub > wwwroot > osTicket > include > Right click on ost-sampleconfig.php and rename it to ost-config.php</p>
<img src="https://i.imgur.com/WpV0rsX.png"/>
<p><h2>Next assign permissions<h2/> </p>
<p> Right click on ost-config.php > click on PROPERTIES > click on SECURITY > click on ADVANCED > Click on DISABLE INHERITANCE</p>
<P> WINDOW WILL POP-UP, make sure to select REMOVE ALL PERMISSIONS > Click SELECT A PRINCIPAL > Type: EVERYONE > Click CHECK NAMES > Click Ok</P>
<img src="https://i.imgur.com/7M23ZPY.png"/>
<p> Check FULL CONTROL > Click Ok > </p>
<img src="https://i.imgur.com/5aYEp3c.png"/>
<p> Back to the osTicket webpage and click CONTINUE at the bottom. You have successfully installed osTicket now fill in HELP DESK information </p>
<img src="https://i.imgur.com/6jfbXGw.png"/>
<p> *FILL OUT HELP DESK INFORMATION and REMEMBER when filling out that we already created a password and database for mysql and "root" will always be the username* </p>

<p> One final step is CLEAN UP ( Delete setup and change permissions back to read only )</p>
<p><h2> To delete setup folder go to: Delete: C:\inetpub\wwwroot\osTicket\setup <h2/>
<p><h2> To change permissions go go to: Windows (C:) Drive > wwwroot > osTicket > Include > scroll down to find ost-config.php and Right click on Properties > Click SECURITY > ADVANCED > Click on EVERYONE > EDIT to only READ and EXECUTE > Click Ok > APPLY <h2/> </p>
<P> Log into osTicket</P>
<img src="https://i.imgur.com/MOz6Mid.png"/>

Thankyou for reading.
