# Create Simple Network
![Simple Network](https://github.com/0xbythesecond/Create-Simple-Network/assets/23303634/8105ef82-82c7-4f45-a589-d3e90c316b50)




## Objective:
The objective of this lab is to configure a simple network with multiple devices connected through a router and switches.

### Topology Setup:
- Open Packet Tracer and select the router, two switches, four computers, and two printers.
- Drag and drop the devices onto the workspace.
- Connect one switch to each side of the router using Ethernet cables.
  -  > Note : Press control (CTRL) on your keyboard and the automatically choose connection type icon <img  width="200" alt="automatically choose connection type icon" src="https://github.com/0xbythesecond/Create-Simple-Network/assets/23303634/7cee14fe-3efd-429e-9530-32b1fc5af887"/> and you can connect each of these devices on the network.
- Connect two computers and 1 printer to each switch.

<p align=center><img src="https://github.com/0xbythesecond/Create-Simple-Network/assets/23303634/0bef1a0e-d3f6-4879-bdc9-81a0d8386f96" width="700" alt="packet tracer setup"/></p>


### Configuration of Router Interfaces:
- Access the router's Command Line Interface (CLI) by clicking on it and selecting "Command Line Interface."
       
<p align=center><img src="https://github.com/0xbythesecond/Create-Simple-Network/assets/23303634/7e6e93dd-8834-4ce9-9abe-c23456220523" width="600" alt="select router cli"/></p>

- First you will be prompted with `Continue with configuration dialog? [yes/no]:` and here you will enter `no` as it will not be needed and typically not needed in many instances. 
- Enter global configuration mode initially by using the `enable` (privileged EXEC mode) command and then to enter the global configuration mode by entering `configure terminal` or `conf t` for short.
  
<p align=center><img src="https://github.com/0xbythesecond/Create-Simple-Network/assets/23303634/3a2d325d-022d-478e-a9d8-3edc7d835f08" width="500" alt="enter global configuration mode"/></p>

- Configure IP addresses for each router interface (g0/0/0 and g0/0/1) using the interface and ip address commands.
- For this example, interface gigabitethernet0/0/0 followed by ip address 192.168.0.1 255.255.255.128 and this will represent a /25 network with the ability to have 126 host on the network. This is definitely more than we need, but this allows for us to expand the network if needed in the future.
- Configure interface gigabitethernet0/0/0 and `no shutdown` (`no shut`) command on this interface, this is instructing the router to bring that interface up, allowing traffic to flow through it. Just for clarity here, this `no shutdown` command is typically used after configuring an interface or resolving any issues that may have caused it to be shut down.
  - Configure ip address for interface g0/0/0 ![configure ip address g000](https://github.com/0xbythesecond/Create-Simple-Network/assets/23303634/3c55c265-5708-4353-b4b9-7fe0a36799f7)
  - Configure ip address for interface g0/0/1 ![configure ip address router g001](https://github.com/0xbythesecond/Create-Simple-Network/assets/23303634/044433a5-4b63-414a-820d-6c2674fa970a)

### Configuration of Switches (with Port Security):
- Click on Switch0 to access its configuration panel and select the CLI tab.
  - ![switch0 cli tab](https://github.com/0xbythesecond/Create-Simple-Network/assets/23303634/5b0d4a79-0ead-4841-ba77-f92857e9551d)
 
- We will first need to enable port security while in global configuration mode for the interface range fa0/1-3 with the commands `int range f01/-3 `switchport mode access` and then `switchport port-security`.
- After port security is enabled, we will configure port security features for the interface range 1, 2 & 3 with sticky MAC addresses using the `switchport port-security mac-address sticky command`. 
  - ![enable port security for switch0](https://github.com/0xbythesecond/Create-Simple-Network/assets/23303634/d52ed17b-815a-49e8-8afc-5f06bc3f6de4)
    - > Note: The error lets me know that I forgot something or entered something incorrectly and in this instance, it was the "-" between port-security.

- We also enabled violation mode protect (`switch(config-if)#switchport port-security violation protect`
  ). When violation mode is configured, the switch quietly discards any traffic from unauthorized MAC addresses without taking any further action. This mode is useful in scenarios where you want to monitor and log unauthorized access attempts without disrupting network connectivity. For further clarity here, if a violation is detected, the switch will take no action to restrict or shut down the port on the switch. Instead, it will simply drop any frames from violating MAC addresses without generating any alerts or notifications.
- After sending a ping from PC0 to PC1 and Printer0, we can see that port security has been enabled and has a securesticky type
  - ![show port security is enabled on each of the ports](https://github.com/0xbythesecond/Create-Simple-Network/assets/23303634/d6ef7ae4-6ae7-45f8-bff9-dfde7061dcfe)
  - We will also apply this to Switch1 as well
    - ![show port security is enabled on each of the ports2](https://github.com/0xbythesecond/Create-Simple-Network/assets/23303634/5c7fb47e-4c46-4248-8298-2827e0131307)
 
### Configuration of Computers and Printers:
- Click on each computer and printer to access their configuration panels.
- Assign IP addresses, subnet masks, default gateways, and DNS servers to each device.
  - Default gateway for PC0 & PC1 <br/> <img src="https://github.com/0xbythesecond/Create-Simple-Network/assets/23303634/cff207b9-c931-41e3-93a3-8e6d3b1698c5" width="500" alt="configure ip address pc0"/>
  - With PC0 selected, choose Desktop and then choose IP Configuration <img src="https://github.com/0xbythesecond/Create-Simple-Network/assets/23303634/3a070c76-a59d-46da-afb5-12e2c71da7f9" width="500" alt="configure ip address pc0 step 1"/>
- Use IP addresses within the same subnet as the corresponding router interface.
  - PC0 (192.168.0.2), PC1 (192.168.03) & Printer0 (192.168.0.4) each with a subnet mask of 255.255.255.128 and default gateway of 192.168.0.1.
  -  <img src="https://github.com/0xbythesecond/Create-Simple-Network/assets/23303634/54e94dde-5097-4c7f-bb3e-445be6f22916" width="500" alt="configure ip address pc0 step 2"/>
    - <img src="https://github.com/0xbythesecond/Create-Simple-Network/assets/23303634/5af01582-7c38-4685-8e66-5892dcfff261" width="500" alt="printer0 ip address"/>
    - <img src="https://github.com/0xbythesecond/Create-Simple-Network/assets/23303634/a9a23b61-e7bb-4900-ad7c-c2c58ab5e1a9" width="500" alt="printer0 default gateway"/>

  - PC2 (192.168.0.130) PC3 (192.168.0.131) & Printer1 (192.168.0.132) each with a subnet mask of 255.255.255.128 and default gateway of 192.168.0.129.
  - ![configure ip address pc2](https://github.com/0xbythesecond/Create-Simple-Network/assets/23303634/3e4cfa9d-7787-47fd-a6ba-87196511d7b5)
- Optionally, configure static MAC addresses on the computers and printers to ensure compatibility with port security.

###  Testing Connectivity:
- Test connectivity between computers and printers on both sides of the router using the `ping` command in the Command Prompt.
  - Here we test the connectivity from PC2 to PC3 ![test connectivity from pc2 to pc3](https://github.com/0xbythesecond/Create-Simple-Network/assets/23303634/1d435fc3-777c-4f44-bd43-4b7918c1e19f)
  - Next, we will test the connectivity from PC2 to PC1 to verify that there can be communication outside of the local network for computers/printer PC2, PC3 and Printer0. The first packet fails as it is going through the process of ARP (Address Resolution Protocol) and has to resolve the IP address to a MAC address. 
  - ![test connectivity from pc2 to pc1](https://github.com/0xbythesecond/Create-Simple-Network/assets/23303634/38b309a1-1cd9-4351-a546-70aefc1c6508)


Dispalys the assigned IP addresses, intefaces and devices used for the lab
![image](https://github.com/0xbythesecond/Create-Simple-Network/assets/23303634/d4fe4ce1-50bd-4852-b5f6-96bfff185c82)


### Conclusion:
In conclusion, this lab exercise provided a hands-on opportunity to configure a simple network infrastructure with multiple devices interconnected through a router and a switch. By following the step-by-step instructions, we successfully set up the network topology, configured router interfaces, enabled port security on the switch, and configured the IP addresses and settings for computers and printers.

One of the key takeaways from this lab is the importance of network security. By implementing port security on the switch, we enhanced the security posture of the network by restricting access to authorized devices only. This helps prevent unauthorized access and potential security breaches, thereby safeguarding sensitive information and resources on the network.

Overall, the skills and knowledge gained from this lab can be directly applied in real-world scenarios, especially in designing, configuring, and securing small to medium-sized networks. Understanding how to set up basic network infrastructure elements and implement security measures is essential for building resilient and secure networks in various environments.
