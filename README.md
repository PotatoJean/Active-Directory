<h1>Setting up Home Lab running Active Directory</h1>

<h2>Description</h2>

Active Directory is often used as an Identity Provider which is used to create, maintain and manage identity information. In short, Active Directory is used to keep track of resources and control access of users in one way or another.</br>
</br>
Goal of Project: to setup a basic home lab running active directory and create a bunch of users using powershell script.
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Oracle Virtual Box</b>
- <b>Active Directory</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)
- <b>Windows Server</b> 
  
 <p align="center">
  <img src="https://i.imgur.com/egvCvHr.png" height="80%" width="80%" alt="Change mod of shell script"/><br/>
   <p>
The following project is done referencing to the information provided in the diagram above<br/>
 </p> <br/>
 
<h2>Project screenshots:</h2>

<p align="center">
Creating the Active Directory <br/>
  <p>
<p align="center">
-Upon setting up the Windows Server as the domain controller on Virtual Box, Server Management dashboard will be displayed<br/>
-Click on add role and features<br/>
 </p> <br/>
 <br/>
 <p align="center">
<img src="https://i.imgur.com/xtqw5qa.png" height="80%" width="80%" alt="Change mod of shell script"/>
<br />
<br />

 <p>
-Select the server role (Active Directory Domain Services) and start the installation.<br/>
 </p> <br/>
 <br/>
 <p align="center">
<img src="https://i.imgur.com/s63rv0L.png" height="80%" width="80%" alt="Change mod of shell script"/>
<br />
<br />

<p align="center">
Configure Post-Deployment of Active Directory <br/>
  <p>
-Installation of Active Directory does not mean creation of domain controller.<br/>
-Click on "promote this server to domain controller"<br/>
 </p> <br/>
 <br/>
 <p align="center">
<img src="https://i.imgur.com/4YEfQ3f.png" height="80%" width="80%" alt="Change mod of shell script"/>
<br />
<br />

 <p>
-Set the root domain name and the Directory Services Restore Mode (DSRM) password. <br/>
-Follow the default settings and install the Active Directory Domain Services. <br/>
 </p> <br/>
 <br/>
 <p align="center">
<img src="https://i.imgur.com/YryLSJh.png" height="80%" width="80%" alt="Change mod of shell script"/>
<br />
<br />

 <p>
-The machine will prompt for a reboot and the following page indicates the successful installation. <br/>

 </p> <br/>
 <br/>
 <p align="center">
<img src="https://i.imgur.com/MaoYREs.png" height="80%" width="80%" alt="Change mod of shell script"/>
<br />
<br />

<p align="center">
Creating a new user (Admin) <br/>
  <p>
-Start off by creating organization unit (think of it as a folder to store the type of users).<br/>
-Name the folder accordingly.<br/>
 </p> <br/>
 <br/>
 <p align="center">
<img src="https://i.imgur.com/cFizJEc.png" height="80%" width="80%" alt="Change mod of shell script"/>
<br />
<br />
   
<p>
-Create the user after creation of organization unit. <br/>
-Set the username and password for the user. Manually set the user with admin role. <br/>
 </p> <br/>
 <br/>
 <p align="center">
<img src="https://i.imgur.com/grqUVc0.png" height="80%" width="80%" alt="Change mod of shell script"/>
<img src="https://i.imgur.com/eEb2qof.png" height="80%" width="80%" alt="Change mod of shell script"/>
  
<br />
<br />

<p>
-Instead of signing it with the way previously used, we can now sign in as the admin we just created. <br/>

 </p> <br/>
 <br/>
 <p align="center">
<img src="https://i.imgur.com/eEb2qof.png" height="80%" width="80%" alt="Change mod of shell script"/>

  
<br />
<br />

<p align="center">
Creating Remote Access <br/>
  <p>
-Now that we are finished with creating a user, we would like to create remote access.<br/>
-Stick to the default settings and install the service.<br/>
 </p> <br/>
 <br/>
 <p align="center">
<img src="https://i.imgur.com/XLIUfHO.png" height="80%" width="80%" alt="Change mod of shell script"/>
<br />
<br />

<p>
-Go to Tools > Routing and Remote Access on the top right corner of Server Manager Panel. <br/>
-Click on configure and enable routing and remote access. <br/>
-Set the configuration as NAT, Network Address Translation to allow internal clients to connect using one public IP address.<br/>
 </p> <br/>
 <br/>
 <p align="center">
<img src="https://i.imgur.com/dNihrZS.png" height="80%" width="80%" alt="Change mod of shell script"/>

  
<br />
<br />
<p>
-A successful configuration will make the icon beside the DC green as shown below <br/>

 </p> <br/>
 <br/>
 <p align="center">
<img src="https://i.imgur.com/nieS59g.png" height="80%" width="80%" alt="Change mod of shell script"/>

  
<br />
<br />


<p align="center">
Setting up DHCP server on Domain Controller <br/>
  <p>
-This step is done so that the internal client can have an IP address assigned to them automatically.<br/>
-Select DHCP service, follow the default settings and install the service.<br/>
 </p> <br/>
 <br/>
 <p align="center">
<img src="https://i.imgur.com/nJjcl43.png" height="80%" width="80%" alt="Change mod of shell script"/>
<br />
<br />

<p>
-Setup the scope for IPv4 <br/>
-Upon completion of setup, right click on the domain and click refresh to see the effects.<br/>
 </p> <br/>
 <br/>
 <p align="center">
<img src="https://i.imgur.com/ZXqbP0k.png" height="80%" width="80%" alt="Change mod of shell script"/>
<img src="https://i.imgur.com/n0BBE8U.png" height="80%" width="80%" alt="Change mod of shell script"/>
  
<br />
<br />

<p align="center">
Running script on PowerShell ISE <br/>
  <p>
-In this step, we run a script to set a list of randomize names as the users in the Active Directory.<br/>

 </p> <br/>
 <br/>
 <p align="center">
<img src="https://i.imgur.com/lc0XAZw.png" height="80%" width="80%" alt="Change mod of shell script"/>
<br />
<br />

   <p>
-Check the users created under the organization unit of "_USERS"<br/>

 </p> <br/>
 <br/>
 <p align="center">
<img src="https://i.imgur.com/yq8nBVK.png" height="80%" width="80%" alt="Change mod of shell script"/>

  
<br />
<br />

<p align="center">
Setting up Windows 10 Client machine on Virtual Box <br/>
  <p>
-We will check the IP address and default gateway to verify whether we have done previous steps correctly.<br/>
-If the default gateway exist, we can check it functionality by pinging a website.<br/>
-Pinging successfully indicates that the DNS server configured previously is working.<br/>
 </p> <br/>
 <br/>
 <p align="center">
<img src="https://i.imgur.com/OKBz3mT.png" height="80%" width="80%" alt="Change mod of shell script"/>
<br />
<br />

<p align="center">
Checking the lease on Windows Server <br/>
  <p>
-When we created our client machine and join it to the network, it reached out to the DHCP to get an IP assigned to it.<br/>
-In other words, if any client gets an address it will show up here.<br/>

 </p> <br/>
 <br/>
 <p align="center">
<img src="https://i.imgur.com/ZehWAHe.png" height="80%" width="80%" alt="Change mod of shell script"/>
<br />
<br />

   <p>
-The client computer can be now found inside the Active Directory, meaning that the client can logon to the network using username and password assigned to them.<br/>

 </p> <br/>
 <br/>
 <p align="center">
<img src="https://i.imgur.com/KNLdlp0.png" height="80%" width="80%" alt="Change mod of shell script"/>

  
<br />
<br />

   <p align="center">
Verifying eligibility of logging in <br/>
  <p>
-Doing everything correctly will grant the user access to login to mydomain that is previously created.<br/>
-We can now run "whoami" in Command Prompt on the client computer to verify the user who is logged onto mydomain.<br/>

 </p> <br/>
 <br/>
 <p align="center">
<img src="" height="80%" width="80%" alt="Change mod of shell script"/>
<br />
<br />
   
<p>That's all for this project, thanks for reading this far. This is a lengthy documentation, I struggled here and there but it was fun learning something new. </br></p>



<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
