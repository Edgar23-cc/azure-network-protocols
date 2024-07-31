<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Video Demonstration</h2>

- ### [YouTube: Azure Virtual Machines, Wireshark, and Network Security Groups](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Step 1: Creating two Virtual Machine from azure and have on for windows and the other for Linux with the same resource group and vnet. If easier you can use the same username and password for both VMs. Open and run destop remote put the IP Address that azure provided you that would be under "Public IP Address" you want use a different account and put in username and password that you used in azure when creating the windows vm, Now you would be able run the windows vm. 
- Step 2: When you are in the windows vm open "mirosoft edge" and search wireshark in the window virtual machine.
- Step 3: When you finish downloading wireshark open and run, filter it for icmp only so you can see the traffic when ping a something on the command line or powershell. You can ping the private IP Address from Linux vm. 
- Step 4: Now that you pinged the Linux private IP Address you can do a perpetual/non-stop ping while the ping is running you want to go to linux vm's Network security and create a new imbound name it "deny icmp ping from anywhere" set as decline.  Go back to check the non-stop ping now you will notice that it can't ping vm linux because that imbound rule is taking effect 
- Step 5:

<h2>Actions and Observations</h2>
ICMP Traffic/NSG
<p>
 
 Allowing Request 
<img src="https://i.imgur.com/32kmuuv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 
 Decline Request 
  <img src="https://i.imgur.com/AWwX4KC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
SSH Traffic
<p>
<img src="https://i.imgur.com/qai9SZA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
DNS Traffic
<p>
<img src="https://i.imgur.com/F48S2Tf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
