<h1>Windows 10 VM Creation and Joining to an Active Directory Domain</h1>

<!-- ### [YouTube Demonstration](https://youtu.be/7eJexJVCqJo) -->

<h2>Description</h2>
This lab will demonstrate a walk-thru of setting up a Windows 10 Pro installation in Virtual Box making sure to  
provision enough resources and applying the correct settings for a smooth experiene. It will also demonstrate 
joining it to an already existing domain.
<br />


<h2>Languages and Utilities Used</h2>

- <b>Windows Server</b>
- <b>Virtual Box</b>

<h2>Environments Used </h2>

- <b>Windows Server</b>
- <b>Windows 10 Pro</b>
- <b>Virtual Box</b>

<h2>Program walk-through:</h2>

<p align="center">
First, download The Media-Installation Tool from Microsoft. This tool will be used to create an image file that we'll used to install Windows 10 later: <br/>
<img src="https://i.imgur.com/l9qzwc1.png" height="80%" width="80%" alt="VM and Server 2016 Steps"/>
<br />
<br />
Specify creating an installation media:  <br/>
<img src="https://i.imgur.com/yzbLnBR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Next, determine what the architecture of the system is (32-bit or 64-bit) and choose the appropriate option. We're running a 64-bit machine so we'll choose that: <br/>
<img src="https://i.imgur.com/635aZqQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Since we're going to utilize a Virtual Machine we'll choose to create an ISO file so we can mount it.: <br/>
<img src="https://i.imgur.com/QCBShsw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br /> 
Windows 10 will begin to download and our ISO file will be created after its done.:  <br/>
<img src="https://i.imgur.com/zCMykxq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Let's make sure we give the VM enough memory to run the OS, but not so much that it causes our physical system to crash or lag:  <br/>
<img src="https://i.imgur.com/BEMripe.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
We'll allocate some Processor Cores to the VM so we can run our programs:  <br/>
<img src="https://i.imgur.com/5N1TAgV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
We've setup our Domain in such a way that the Domain Controller is responsible for DNS, NAT, and DHCP so we can use an Internal Network on our Windows 10 VM to join our domain:  <br/>
<img src="https://i.imgur.com/ZHhNDip.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
We're going to enable Hyper-V to help with the smoothness of operation:  <br/>
<img src="https://i.imgur.com/fg4AGZE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Let's start the Windows 10 Installation:  <br/>
<img src="https://i.imgur.com/Iop3wZU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Choose Windows 10 Pro for the installation since we'll be operating in a Professional Environment it gives us options and featurese that Windows 10 Home doesn't have.  <br/>
<img src="https://i.imgur.com/4bsgzqO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Windows 10 has been installed and we're logged in.:  <br/>
<img src="https://i.imgur.com/dwU28JJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
We need to change our DNS settings to point to our Domain Controller's IP so we can use it for DNS:  <br/>
<img src="https://i.imgur.com/hsiVq8C.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Let's join this to our Active Directory Domain. First we navigate to Advanced System Settings:  <br/>
<img src="https://i.imgur.com/jmlt9HO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Now we'll click change to get to Change our Computer name, but more importantly we'll be presented with the option to Join a Domain:  <br/>
<img src="https://i.imgur.com/wpB3RtB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
We have to Authorize the Domain Addition by logging in with an account that is ALREADY a part of the DOMAIN (not the local machine). We're using the "Adminstrator" account here:  <br/>
<img src="https://i.imgur.com/tL9jXVo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
We've successfully joined the domain, Lets check our Domain Controller and see what shows up...:  <br/>
<img src="https://i.imgur.com/hbTfEIq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
In our Domain Controller, we can see we have an IP Address Lease from COMP-001 (our newly joined Computer):  <br/>
<img src="https://i.imgur.com/XtPcY32.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
We can also see we have a new addition in Active Directory Users and Computers with our newly joined Computer:  <br/>
<img src="https://i.imgur.com/SRtdW08.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
