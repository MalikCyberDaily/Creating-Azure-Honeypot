# Creating-Azure-Honeypot
<h2>Configuring Honeypot VMs in Azure</h2>

![ConfigureHoneynet](https://i.imgur.com/OeCPjoX.png)

<b>To create the open vulnerable environment, the first step is to deploy 2 virtual machines and configure the NSGs to allow inbound connections from any source to any port:</b>
- Log into your Azure account and select Virtual Machines.
- Click on (+) to create a new virtual machine (One running Linux and another running Windows)
- Ensure both VMs are on the same Resource Group, Region, and VNet(i.e 10.1.0.0/16)
- Create each VM with a strong username and password
- After creating the Windows VM, RDP into the machine and turn off all windows firewall settings via **wf.msc**

![DisableFW](https://i.imgur.com/g5PAPsr.png)
  
- Go back to Azure and go to Network Security Groups
- For each VMs NSG, Add a new rule to allow all inbound connections to all ports. Set the priority to the lowest one to ensure this rule will be followed first.
- A simple, but effective Azure honeypot has been configured!

![NSGAllowALL](https://i.imgur.com/Q850lM4.png)

A quick tip, run ping -t [vm's ip address] on your host machine to verify if connection is being allowed
![ping](https://i.imgur.com/MMibipV.png)
