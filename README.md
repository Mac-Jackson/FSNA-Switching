<p align="center">
<img src="https://github.com/user-attachments/assets/53f9a48d-68ef-41b3-9119-e302dc2d49bc"/>
</p>

<h1>Core Switch Basic Configuration</h1>
This Lab tutorial outlines how to configure a new switch out of the box.<br />




<h2>Networking Technologies Used</h2>

- Cisco Networking
  


<h2>Environments Used </h2>

- Command-Line Interface (CLI)


<h2>Tools Used </h2>

- Cisco Packet Tracer


<h2>Security Features </h2>

- Global Password Encryption
- VTY Access Control Lists

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1  Configure Hostname
- Step 2  Enable Secret
- Step 3  Configure Clock
- Step 4  Configure Management IP Address
- Step 5  Configure Local Username & Password
- Step 6  Configure Global Password Encryption Service
- Step 7  Configure VTY line Access Control List

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/1KNzrMo.png" height="80%" width="80%" alt="FSNA-SW1"/>
</p>
<p>
Console into Switch from NOC-PC.
</p>
<br />

<p>
<img src="https://i.imgur.com/UImkSMc.png" height="80%" width="80%" alt="FSNA-SW1"/>
</p>
<p>
Configure Hostname, Enable Secret, & Clock.  #clock set hh:mm:ss DD MONTH YYYY
 (config)#hostname FSNA-SW1
 (config)#enable secret fsnalab
</p>
<br />

<p>
<img src="https://i.imgur.com/Rjgb3j0.png" height="80%" width="80%" alt="FSNA-SW1"/>
</p>
<p>
Configure Management IP Address & Local Username & Password. (config)#interface vlan 100
 (config-if)#ip address 192.168.100.251 255.255.255.0
 (config)#ip default-gateway 192.168.100.1
 (config)#username fsna password zte
 (config)#service password-encryption
 (config)#line console 0
 (config-line)#login local
</p>
<br />

<p>
<img src="https://i.imgur.com/II0mKB1.png" height="80%" width="80%" alt="FSNA-SW1"/>
</p>
<p>
Configur Global Password Encryption. (config)#service password-encryption
</p>
<br />

<p>
<img src="https://i.imgur.com/nI9RjJv.png" height="80%" width="80%" alt="FSNA-SW1"/>
</p>
<p>
Configure VTY Access Control List. (config)#ip access-list standard VTY
 (config-std-nacl)#permit 192.168.100.0 0.0.0.255
 (config)#line vty 0 15
 (config-line)#login local
 (config-line)#access-class VTY in
</p>
<br />



