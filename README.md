<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- osTicket Installation Files
- Heidi SQL


<h2>Installation Steps</h2>
<img width="856" height="747" alt="Screenshot 2025-10-01 at 3 53 30 PM" src="https://github.com/user-attachments/assets/16f125f8-ea15-4319-a1fc-e18aa2e296a5" />





We’ll begin by setting up a virtual machine (VM) in the Microsoft Azure portal. A virtual machine provides an isolated environment that behaves like a real computer but runs in the cloud. This approach is safer and more practical than using your personal computer, since it allows you to test, configure, and experiment without affecting your main system.<p>
<img width="440" height="239" alt="remote desktopScreenshot 2025-10-01 at 4 29 23 PM" src="https://github.com/user-attachments/assets/87228bfd-2fa7-43a9-8c37-37c28c04b9f2" />
</p>
<p>Next Connect to your Virtual Machine. To access your virtual machine, open the Microsoft Remote Desktop application on your computer. In the connection window, enter the public IP address assigned to your virtual machine. Once you’ve done that, the system will prompt you to provide your username and password. After entering your credentials, click Connect, and you’ll be logged into your virtual machine, ready to begin working.
</p>
<br />

<p>
<img <img width="227" height="248" alt="image" src="https://github.com/user-attachments/assets/153d816d-6058-4e65-af3a-408dfdf57818" />
</p>
<p>
Once you’ve connected to your virtual machine, the next step is to install and extract the osTicket-Installation-Files folder. Once you have done that, move the osTicket-Installation-Files folder to your desktop, and it should appear similar to the example shown in the image above.
We’re installing this folder because it contains all of the required files and resources needed to set up osTicket in one convenient location. Keeping everything organized in a single folder will make the installation process smoother and easier to follow.</p>
<br />

<p>
<img <img width="1128" height="591" alt="image" src="https://github.com/user-attachments/assets/c536992d-3dbb-444d-a7ca-5ef403cbb35e" />

</p>
<p>
Next we are going to enable IIS. To enable IIS, start by opening the Control Panel on your computer. From there, go to Programs and select Uninstall a program. On the left-hand side of the window, click Turn Windows features on or off. A new window will appear with a list of optional Windows features. Scroll down until you find Internet Information Services (IIS), then check the box next to it.</p>
<br />
<img width="421" height="376" alt="image" src="https://github.com/user-attachments/assets/13c6c2ab-c1f8-4c39-8ad1-bfa74ee2b388" />



Now that IIS is enabled, the next step is to install the CGI feature. To do this,  expand Internet Information Services by clicking the plus sign. Next, expand World Wide Web Services, and then expand Application Development Features. From there, locate CGI and check the box beside it. Once you’ve selected it, click OK to apply the changes.



<img width="499" height="405" alt="image" src="https://github.com/user-attachments/assets/e2471115-b784-4607-b097-367b872fb555" />





Now that IIS and CGI are enabled, the next step is to install PHP Manager for IIS. This is important because osTicket runs on PHP, which is a server-side scripting language. Without PHP installed and configured, osTicket will not function properly. To begin, open your osTicket installation files folder and double-click the file named PHPManagerForIIS_V1.50. The installation wizard will launch, and you can proceed by clicking Next. When prompted, accept the license agreement by selecting I Agree. The installer will then begin setting up PHP Manager. Once the installation is complete, you should see a confirmation screen similar to the image above. At this point, you can click Close to finish the process.

<img width="495" height="387" alt="image" src="https://github.com/user-attachments/assets/1f0cb826-31d0-4bcc-ac49-68d945d2a8d6" />


Next, we will install the Rewrite Module, which is required for proper URL handling in osTicket. To begin, open your osTicket installation files folder if you are not already there. Locate the file named rewrite_amd64_en-US.msi and double-click it to launch the installer. When the setup window appears, select Install to start the installation process. After it has finished, click Finish to close the installer.

<img width="495" height="387" alt="image" src="https://github.com/user-attachments/assets/80a3b527-2007-43fe-98e2-bd68d6c2e87b" />

Next we will install MySQL 5.5.62. Simply open the osTicketInstallationFiles folder and double-click on MySQL-5.5.62-win32. The installer will launch, and you can proceed by clicking Next. When you reach the server setup screen, choose the Typical Setup option to ensure a standard installation. After selecting it, click Install and wait for the process to complete. When the installation finishes, a confirmation window will appear, similar to the image shown below. At this point, do not click Finish, as leaving this window open is essential for the next step in the setup process.

<img width="500" height="381" alt="image" src="https://github.com/user-attachments/assets/94ac9301-bea5-45c8-812f-04a9b7d41000" />



Once the installation has finished, you’ll be prompted to launch the MySQL Configuration Wizard. Begin by clicking Finish in the Server Setup window. When the wizard opens, click Next to move forward. On the next screen, select Standard Configuration and continue by clicking Next. You’ll be asked to confirm again, so simply click Next once more. When you arrive at the Security Options screen, you’ll need to set up the username and password. For this tutorial, type ROOT as both the username and password. This approach is not secure and should never be used in a real-world environment, but it will keep things simple here and ensure there’s no confusion with credentials. After entering the details click Next, then choose Execute to apply the configuration.

<img width="959" height="58" alt="image" src="https://github.com/user-attachments/assets/f5455d2a-3ffd-4c85-adad-c0fa7f53f227" />

Next, we’ll begin installing osTicket v1.15.8. Start by opening your osTicket-Installation-Files folder and locating the folder named osTicket-v1.15.8. Right-click on this folder and choose “Extract All”. When the extraction window opens, simply click Extract. A new folder will be created containing the extracted files. Open that folder, and you should see the same contents as the example shown in the image above.

<img width="656" height="99" alt="image" src="https://github.com/user-attachments/assets/9e2168c9-7b14-4d06-9b7d-eaf966d34f12" />

The next step is to move the Upload folder into the wwwroot directory and rename it to osTicket. To do this, open a new File Explorer window and navigate to your C: drive. From there, open the inetpub folder and then the wwwroot folder. Once inside wwwroot, return to your extracted osTicket-v1.15.8 files, locate the Upload folder, and drag it into the wwwroot directory. After the folder has been copied, right-click it, choose Rename, and change its name to osTicket.
