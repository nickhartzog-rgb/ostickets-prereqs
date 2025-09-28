<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket. A lot of tutorials just give you a step-by-step to do and don't really break them down any further for those that have no prior experience in this area, my guide will be as detailed and new user friendly as I can make it. Any questions or suggestions for more clairity anywhere just contact me on my linked social accounts.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10 Pro, version 22H2 - x64 Gen2</b>

<h2>List of Prerequisites</h2>

- Azure Subscription
- Resource Group
- Windows 10 pro Virtual Machine(VM)
- osTicket Zip Files
  
<h2>Installation Steps</h2>

<p>
<img width="1918" height="902" alt="image" src="https://github.com/user-attachments/assets/d3501749-b4d1-48c6-abc3-e6d3673cdc06" />

</p>
<p>
Please ensure that you have accessed this document from within the virtual machine by entering the URL provided at the top of the page into a web browser inside the VM. Once the document is open in the VM's browser, locate the link included in the document to download the osTicket ZIP files directly onto the virtual machine. Once the file has been downloaded go to your downloads folder in your computer files and you should see the osTicket zip files. From there we'll drag the file straight to the desktop, once it's there right click it and hit extract all, make sure when you hit "extract all" its going to the desktop folder. You should see the file you just extracted on your desktop. We can now just trash the zip file, (NOT THE ONE WE JUST EXTRACTED).
</p>
<br /> 

<p>
<img width="911" height="505" alt="image" src="https://github.com/user-attachments/assets/f7353d12-a194-465e-823e-6dc3c184fd8d" />

</p>
<p>
We're installing the webserver now, to enable IIS we go to the start button and then the Control Panel. From there you should see Programs on the bottom, we're going to click "Uninstall a Program" we won't be doing that it just takes us to the page we need to go. Once in that section we'll go to "Turn Windows Features On or Off" and thats where we'll find "Internet Information Services" it should have an empty box next to if, we'll go ahead and check it. We also want to install or enable CGI while we're here. CGI is a just something osTicket needs, you'll find it under World Wide Web Services, and under Applicant Development Features. Then once both are check we'll click "OK" and wait while they install. I apologize for the blur on the image but I hope it still gives you an idea of what the place looks like that you should be at in install/enable these features.
</p>
<br />

<p>
<img width="582" height="481" alt="image" src="https://github.com/user-attachments/assets/1d510f2f-19c7-47fc-9452-241857ec075b" />

</p>
<p>
Next, from the osTicket installation files folder, we'll install PHP manager for IIS. PHP is like a backend webserver language, and osTicket runs on PHP. We'll start by going into the osTicket installation file we unzipped on the desktop earlier. Once we've opened the file we should see PHP manager, double click on it and then just hit "next," "I, agree - Next," and finally just hit, "Yes" and it should begin installing. From within the same file we'll install the "Rewrite Module" it will be right under the one we just installed. The rewrite module is used to clean up and simplify URLs, making them more user-friendly, readable, and sometimes more secure. 
</p>

<p>
<img width="513" height="485" alt="image" src="https://github.com/user-attachments/assets/5f578df4-578b-49f2-ac65-9bc310e6e783" />

</p>
<p>
We'll now be creating a directory on the c-drive called PHP. The c-drive can be found when you open file explorer towards the bottom on the left called "Windows (C:)" and once you've opened the c-drive folder right click in it and create a new folder called "PHP". From here we'll go back to the “osTicket-Installation-Files” folder, and unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the PHP folder we just made on the c-drive. So we'll go ahead and righ click the zip file PHP which hold the binaries like, the language itself, and click "extract all". and before we extract it we want to click browse and select the PHP folder on the c-drive we just made, then export it. 
</p>

<p>
<img width="811" height="477" alt="image" src="https://github.com/user-attachments/assets/9fa60536-2564-43e5-984b-20978422b800" />

</p>
<p>
Next we'll install VC_redist.x86.exe. from the osTicket installation folder. Once you see it go ahead and double click on it. It'll open a little window before it installs, just click agree and hit install, then click yes on the next page. Now we'll install MySQL, this is simply a database for osTicket, it stores all user accounts, all the ticketing information, everything osTicket spits out or recieves from users will be put in this database on the backend. In the very same folder osTicket installation we'll double click on MySQL and just hit next and agree on whatever it prompts, until you get to the screen where is asks you to choose a setup type. Once we get to this page just make sure you have it on "Typical" setup, then click install and then click yes. It'll prompt you yet again, just click "finish" 
</p>












<br />
