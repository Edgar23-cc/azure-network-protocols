<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />




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
- Step 4: Now that you pinged the Linux private IP Address you can do a perpetual/non-stop ping while the ping is running you want to go to linux vm's Network security and create a new imbound name it "deny icmp ping from anywhere" set as decline.  Go back to check the non-stop ping now you will notice that it can't ping vm linux because that imbound rule is taking effect. Now that you saw that imbound was working you can go back to linux Network security and allow the imbound rule you created.
- Step 5: After you allowed the ibound rule that was created the ping will be working again. The traffic of ssh is connecting the windows commmand line with linux the way you access is put the user name that you created in azure while you were creating Linux VM and than the private IP Address of the same virtual machine for example (labuser@10.0.0.5) for reference you look the SSH Traffic picture that would be below, To get out of the SSH system just say "exit" on the command line or powershell that you are using at the time. Now you change the filter for dns to see the traffic on the command system that you are using type nslookup and whatever website such as google or disney it will show the sever and the IP address for that site.

<h2>Actions and Observations</h2>
ICMP Traffic/NSG
<p>
 
 Allowing Request ➡️
<img src="https://i.imgur.com/32kmuuv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 
 Decline Request ➡️
  <img src="https://i.imgur.com/AWwX4KC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
On the picture that says "Allow Request" was before the imbound rule was created and that was allowing the linux VM to reply each time that windows was requesting but as soon the imbound rule was created and it set to deny linux vm couldn't reply just like the picture that says "Decline Request" the only thing it will say is request timeout each the windows vm is requesting. If you allow it again windows will recieve a reply to stop the ping that was made click (control,C). You will see this type of traffic if you are trying to ping something like (ping /all). 
<p>
</p>
<br />
SSH Traffic
<p>
<img src="https://i.imgur.com/qai9SZA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
When you connect to linux you will get some traffic just like the picture above, Using commands like zip to zip files or ifconfig to display the Ip address. The more commands you use the more traffic it will show. Notice that the souce and destination change is because you are using the linux and it has it own private ip address.
</p>
<br />
DNS Traffic
<p>
<img src="https://i.imgur.com/F48S2Tf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 When you are you using the filter dns you can look up the ip addresse(s) of the site you used in the command system just like how it shows the picture above. Notice that google has more than one IP address and disney has just one IP address.The reason why google has ip addresses is because it has more resources than disney has.
</p>
<br />
