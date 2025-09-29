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
- Microsoft Remote Desktop App
- Windows 10 pro Virtual Machine(VM)
- osTicket Zip Files
  
<h2>In Depth Photo Guided Installation Steps</h2>
Step 1
<p> 
<img width="1385" height="475" alt="image" src="https://github.com/user-attachments/assets/b8f13ef5-ef4b-4279-9cd7-c13e45c3ef40" />

</p>
<p>
Please ensure that you have accessed this document from within the virtual machine by entering the URL provided at the top of the page into a web browser inside the VM. Once the document is open in the VM's browser, locate the link included in the document to download the osTicket ZIP files directly onto the virtual machine. Once the file has been downloaded go to your downloads folder in your computer files and you should see the osTicket zip files. From there we'll drag the file straight to the desktop, once it's there right click it and hit extract all, make sure when you hit "extract all" its going to the desktop folder. You should see the file you just extracted on your desktop. We can now just trash the zip file, (NOT THE ONE WE JUST EXTRACTED).
</p>
<br /> 
Step 2
<p> 
<img width="911" height="505" alt="image" src="https://github.com/user-attachments/assets/f7353d12-a194-465e-823e-6dc3c184fd8d" />

</p>
<p>
We're installing the webserver now, to enable IIS we go to the start button and then the Control Panel. From there you should see Programs on the bottom, we're going to click "Uninstall a Program" we won't be doing that it just takes us to the page we need to go. Once in that section we'll go to "Turn Windows Features On or Off" and thats where we'll find "Internet Information Services" it should have an empty box next to if, we'll go ahead and check it. We also want to install or enable CGI while we're here. CGI is a just something osTicket needs, you'll find it under World Wide Web Services, and under Applicant Development Features. Then once both are check we'll click "OK" and wait while they install. I apologize for the blur on the image but I hope it still gives you an idea of what the place looks like that you should be at in install/enable these features.
</p>
<br />
Step 3
<p> 
<img width="582" height="481" alt="image" src="https://github.com/user-attachments/assets/1d510f2f-19c7-47fc-9452-241857ec075b" />

</p>
<p>
Next, from the osTicket installation files folder, we'll install PHP manager for IIS. PHP is like a backend webserver language, and osTicket runs on PHP. We'll start by going into the osTicket installation file we unzipped on the desktop earlier. Once we've opened the file we should see PHP manager, double click on it and then just hit "next," "I, agree - Next," and finally just hit, "Yes" and it should begin installing. From within the same file we'll install the "Rewrite Module" it will be right under the one we just installed. The rewrite module is used to clean up and simplify URLs, making them more user-friendly, readable, and sometimes more secure. 
</p>
<br />
Step 4
<p> 
<img width="513" height="485" alt="image" src="https://github.com/user-attachments/assets/5f578df4-578b-49f2-ac65-9bc310e6e783" />

</p>
<p>
We'll now be creating a directory on the c-drive called PHP. The c-drive can be found when you open file explorer towards the bottom on the left called "Windows (C:)" and once you've opened the c-drive folder right click in it and create a new folder called "PHP". From here we'll go back to the “osTicket-Installation-Files” folder, and unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the PHP folder we just made on the c-drive. So we'll go ahead and righ click the zip file PHP which hold the binaries like, the language itself, and click "extract all". and before we extract it we want to click browse and select the PHP folder on the c-drive we just made, then export it. 
</p>
<br />
Step 5
<p> 
<img width="811" height="477" alt="image" src="https://github.com/user-attachments/assets/9fa60536-2564-43e5-984b-20978422b800" />

</p>
<p>
Next we'll install VC_redist.x86.exe. from the osTicket installation folder. Once you see it go ahead and double click on it. It'll open a little window before it installs, just click agree and hit install, then click yes on the next page. Now we'll install MySQL, this is simply a database for osTicket, it stores all user accounts, all the ticketing information, everything osTicket spits out or recieves from users will be put in this database on the backend. In the very same folder osTicket installation we'll double click on MySQL and just hit next and agree on whatever it prompts, until you get to the screen where is asks you to choose a setup type. Once we get to this page just make sure you have it on "Typical" setup, then click install and then click yes. It'll prompt you yet again, make sure the box to "Launch the MySQL Instance Configuration Wizard" is checked, then just click "finish". We'll then be brought to another page, click yes, then next. It will ask you to select a configuration type, it should default to "Detailed Configuration" we want to change that to "Standard Configuration" then click next, leave the next page alone and click next again. This next part is VERY IMPORTANT! Make sure you input "ROOT" for the password, exactly how it looks in the quotation 
</p>
<br />
Step 6
<p> 
<img width="406" height="292" alt="image" src="https://github.com/user-attachments/assets/84927470-e6a9-4028-926b-b37dd65eaff2" />
  
</p>
<p>
This next part is VERY IMPORTANT! Make sure you input "ROOT" for the password, EXACTLY how it looks in the quotation. In a real life setup, this isn't what you would want to do but for lab purposes we will have this as the password. If you follow along with what I'm doing you won't need to remember this password, you can just come back to this section of the guide and see what I had you set as the password, so don't stress about not being able to remember it later. After that just click "next" then "execute" and wait for it to configure, then lastly, click "finish". 
</p>
<br />
Step 7
<p> 
<img width="616" height="501" alt="image" src="https://github.com/user-attachments/assets/78b0a7e1-298b-417b-a659-e2ed7ca552c6" />

</p>
<p>
Next we'll open IIS as an admin. So just click the windows icon in the botton left and you should just be able to search "IIS" and once you see it, right click on it and click "open as admin" it should just take a second to open. We're going to register PHP from within IIS, this means we're making the web server aware of the existance of PHP on the computer and we're telling it where it is. When IIS is open you will be able to see an icon labled "PHP Manager" and we're gonna go ahead and open it, once it's open click "Register new PHP version" and when that page opens we'll click the three dots to browse for our file, if you remember we put it on the c-drive. So from browsing we'll open the PHP folder from within the c-drive folder, once the folder is open we'll double click on "php-cgi" and it should auto-fill the textbox with that file. Once it has we'll click "ok" and it will register our PHP. Now we'll reload IIS, by stopping and restarting the web server. On the left side of the IIS page, you should see the drop down bar labled "osticket-vm (osticket-vm\lab)" go ahead and right click it and then click "stop", wait a few seconds and then right click again and hit "start" to reload the server.
</p>
<br />
Step 8
<p> 
<img width="591" height="373" alt="image" src="https://github.com/user-attachments/assets/e59f04af-4351-48bc-aaa4-9f3c6b3525c2" />

</p>
<p>
Now we'll install osTicket v1.15.8 from the osTicket-Installation-Files folder. To make things a little less cluttered we can minimize the IIS page so it's not in our way. Back in our osTicket-Installation-Files folder we're gonna unzip our osTicket v1.15.8 by right clicking on it and clicking "Extract All..." and it should default to extracting to the desktop, and thats ok, we'll have it just go to the desktop, so just click extract now. If you see in your osTicket-Installation-Files folder it made the same file we just extracted, but it's no longer a zip file. This extraction should take a little but of time. After it's done it should auto open the folder, but you can just close it because you probably have a lot of file windows open and we don't need it opened from another window. From the same window we extracted it at you can open the unzipped osTicket v1.15.8 from there. You should see two files, "scripts" and "upload" we are going to copy the upload file into “c:\inetpub\wwwroot" so open another window in file explorer if one isn't already open, and go to c-drive, then "inetpub", then wwwroot. Once there go back to the unzipped osTicket-Installation-Files folder and drag the "upload" file over to the other window in the wwwroot folder. Once it's copied in the new folder, rename "upload" to "osTicket" (IN THE wwwroot FOLDER). Now we'll reload IIS again, go ahead and right click labled "osticket-vm (osticket-vm\lab)" and then click "stop", wait a few seconds and then right click again and hit "start" to reload the server. 
</p>
<br />
Step 9
<p> 
<img width="831" height="746" alt="image" src="https://github.com/user-attachments/assets/fc2a407a-f0c5-4314-a0e6-7cbd3d7b50f5" />

</p>
<p>
Now, we'll open another window in file explorer if one isn't already open, and go to c-drive, then "inetpub", then wwwroot. Once there go back to the unzipped osTicket-Installation-Files folder and drag the "upload" file over to the other window in the wwwroot folder. Once it's moved in the new folder, rename "upload" to "osTicket" (IN THE wwwroot FOLDER). Now we'll reload IIS again, (If you don't remember how to get there go to step 7), go ahead and right click labled "osticket-vm (osticket-vm\lab)" and then click "stop", wait a few seconds and then right click again and hit "start" to reload the server. From here if followed along to a T you should be able to load the osTicket site.
</p>
<br />
Step 10
<p> 
<img width="1312" height="622" alt="image" src="https://github.com/user-attachments/assets/98ef953f-7f65-48d2-b1d8-1c0af99b81c8" />

</p>
<p>
In the same window (IIS) we want to make sure "osticket-vm (osticket-vm\lab)" is expanded, from there expand "sites" and lastly "Default Web Site" we should see osTicket go ahead and click on it and when it opens, on the far right of the screen we should see under "Browse Folder" a link to the osTicket site called “Browse *:80” click it, and it shoudld open the osTicket (Installer) site. If it doesn't load for you for whatever reason, you can use the steps above and try to troubleshoot it a little (It might be faster to just restart unfortunately). For right now we can minimize IIS to clear up your screen. From the image provided above or from your own screen if your following along you should notice that some of the extentions are not enabled, we are going to enable some of them, now we aren't going to enable all of them, but we will enable, php_imap.dll, php_intl.dll, php_opcache.dll for this lab. 
</p>
<br />
Step 11
<p> 
<img width="532" height="478" alt="image" src="https://github.com/user-attachments/assets/1095a617-6139-4770-bb46-6f0468e1a0ed" />

</p>
<p>
We will now, be going back to IIS to make some configurations. We can reopen IIS from minimizing earlier (If you closed it no biggie refer to step 7 if you forgot how to open it). From IIS we should already be open to osTicket, if you aren't expand "osticket-vm (osticket-vm\lab)", from there expand "sites" and lastly "Default Web Site" we should see osTicket. With that open we will double click "PHP Manager" and when that opens look under "PHP Extentions" you should see something called "Enable or disable extentsion" go right ahead and click on that. Now we will enable 3 extentions called, (php_imap.dll), (php_intl.dll), (php_opcache.dll). They are kind of just mixed in with the rest of the disabled extentions, so once you find them just click on it and click "enable" and once all three are enabled go back to the osTicket (Installer) site and reload it to see if the changes went through. There should only be two extentions not enabled at the bottom. 
</p>
<br />
Step 12
<p> 
<img width="507" height="477" alt="image" src="https://github.com/user-attachments/assets/43e4ad09-0b0a-4bd9-959f-433c0e1a8fbf" />

</p>
<p>
So we're going to now rename a file in the hardrive that osTicket uses to make configurations. In the c-drive there's a file called (ost-sampleconfig.php) we will rename it from that to (ost-config.php) simply changing it from "sampleconfig" to "config" and then make sure that osTicket has access to make changes to it. to do that we're going to go ahead and open up file exporer if it not already open and go to the c-drive, then inetpub, then wwwroot, then osticket, and finally from there open the "include" file. Once there we will have to scroll down until we find it, once we do, carefully rename it (right click the file to find the rename option), making sure to not mispell anything (it should be "ost-config.php" exactly spelled like that). After it's changed, we're now going to give osTicket access to make changes on the back end, so right click on the newly named file, go to "properties", then security, from there, click "Advanced" and then you should see something called "Disable Inheritence" click on that to strip all current permissions, it will open a prompt make sure to click "remove all inherited permissions from this object" which should wipe out all permissions. From the same page we'll hit "Add" so we can add our own permissions, once thats open click "Select a Principal" as that opens you should see a box labled above as "Enter the object name to select (Examples)" In the box you wanna type "everyone" (this is not a good thing to do in real life but for lab purposes that's what we'll do) and then click "ok" and lastly below what we just did check the box that says "Full Control" then click "ok" once more. You should after all that only see one thing in the permissions section, and it should say, "Allow-- Everyone-- Full control-- None" and if it does at the bottom click "apply" and then "ok" to the next screen, to make sure everything we did is active.
</p>
<br />
Step 13
<p> 
<img width="641" height="730" alt="image" src="https://github.com/user-attachments/assets/94e9a3d3-ea24-447c-aa0a-072aec774ae8" />

</p>
<p>
Now we will go back to the osTicket (Installer) site and click "continue" at the bottom, to continue the setup. Now, on this page it's pretty much just naming the Helpdesk, and admin overseeing the tickets. So for the Helpdesk name I would put something like "Nick's Helpdesk" but if your name was Lori or Kyle you would obviously substitute your name over mine. Next would be the email address and I don't think it matters if you use are real or fake one I just put my work email. For the Admin section just put your name and the email address from the top can't be the same as the admin one. For the username and password, I like to keep it simple and bland as it's just a lab, I put "adminuser" for the user and "Password1" for the password, exactly as it's typed out. Now before we go to the next step we have to make sure to fill out the datatbase correctly.
</p>
<br />
Step 14
<p> 
<img width="526" height="353" alt="image" src="https://github.com/user-attachments/assets/6ca68ced-a2c1-46fa-bf95-762b56bb10fa" />

</p>
<p>
We already created a database earlier so now we just have to login to it and create another database specific to osTicket and provide the credentials to osTickets installer site. So we're gonna go back to osTicket-Installation-Files folder on the desktop, we're gonna open it, then open the folder named the same as the last one and we're gonna install a file called HeidiSQL_12.3.0.6589_Setup which basically allows us to make a connection to our database, configure it and just do stuff in there. So go ahead and double click the file and when it gives you a prompt click "yes" and then click "I accept" the next, next, next until you get to install then click "install" and wait for it to process. It'll prompt you once more, there should be a box that says "launch HeidiSQL" make sure it's checked, and hit finish. When it launches it'll prompt you, just hit "skip", and click "new" it will ask you for a username and password but remember we set it to "ROOT", and "ROOT" for both, after you input the credentials click open (If the username or password fails, you might've did it in lowercase, so try it again like that). So that opened a connection to the database, from here we want to open a database named osTicket. Now there's a a drop-down folder on the left labled "Unnamed" with a little dolphin kinda logo, we're gonna right click on it, and select "Create New" and then database then when we go to name it it needs to be exactly "osTicket" and no variation of that, then click "ok". You should now see it on the left, it will look like "osticket" but don't worry that's just how it appears. 
</p>
<br />
Step 15
<p> 
<img width="526" height="353" alt="image" src="https://github.com/user-attachments/assets/6ca68ced-a2c1-46fa-bf95-762b56bb10fa" />

</p>
<p>
Now we will enter the credentials into the osTicket (Installer) site, (this window should still be open, if it's not refer to step 9)
</p>
<br />























