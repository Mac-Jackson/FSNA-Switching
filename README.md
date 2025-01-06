<p align="center">
<img src="https://github.com/user-attachments/assets/53f9a48d-68ef-41b3-9119-e302dc2d49bc" height="80%" width="80%" />
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
<img src="https://github.com/user-attachments/assets/4b7a4aeb-50a7-4200-b3fe-8c2f56dc5964" height="80%" width="80%" alt="FSNA-SW1"/>
</p>
<p>
Console into Switch from NOC-PC.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/20de0667-1803-4231-ae92-24ccafd7caea" height="80%" width="80%" alt="FSNA-SW1"/>
</p>
<p>
Configure Hostname, Enable Secret, & Clock.  #clock set hh:mm:ss DD MONTH YYYY
 (config)#hostname FSNA-SW1
 (config)#enable secret fsnalab
</p>
<br />


<p>
<img src="https://github.com/user-attachments/assets/49d034d2-c1a0-44e2-9023-f17a2e9ba71a" height="80%" width="80%" alt="FSNA-SW1"/>
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
<img src="https://github.com/user-attachments/assets/3d9b9c31-c257-4a92-a0c6-b470ecf0a199" height="80%" width="80%" alt="FSNA-SW1"/>
</p>
<p>
Configure Global Password Encryption. (config)#service password-encryption
</p>
<br />


<p>
<img src="https://github.com/user-attachments/assets/aa5ff619-3032-47a3-853a-22cdce4a5bcc" height="80%" width="80%" alt="FSNA-SW1"/>
</p>
<p>
Configure VTY Access Control List. (config)#ip access-list standard VTY
 (config-std-nacl)#permit 192.168.100.0 0.0.0.255
 (config)#line vty 0 15
 (config-line)#login local
 (config-line)#access-class VTY in
</p>
<br />



