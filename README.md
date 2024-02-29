# Create Simple Network
![Simple Network](https://github.com/0xbythesecond/Create-Simple-Network/assets/23303634/8105ef82-82c7-4f45-a589-d3e90c316b50)




## Objective:
The objective of this lab is to configure a simple network with multiple devices connected through a router and switches.

### Topology Setup:
- Open Packet Tracer and select the router, one switch, four computers, and two printers.
- Drag and drop the devices onto the workspace.
- Connect one switch to each side of the router using Ethernet cables.
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
- configure interface gigabitethernet0/0/0 and `no shutdown` (`no shut`) command on this interface, this is instructing the router to bring that interface back up, allowing traffic to flow through it. Just for clarity here, this `no shutdown` command is typically used after configuring an interface or resolving any issues that may have caused it to be shut down.
  - Configure ip address for interface g0/0/0 ![configure ip address g000](https://github.com/0xbythesecond/Create-Simple-Network/assets/23303634/3c55c265-5708-4353-b4b9-7fe0a36799f7)
  - Configure ip address for interface g0/0/1 ![configure ip address router g001](https://github.com/0xbythesecond/Create-Simple-Network/assets/23303634/044433a5-4b63-414a-820d-6c2674fa970a)

### Configuration of Switch (with Port Security):
- Click on the switch to access its configuration panel.
- Enable port security on the switch by setting the maximum number of allowed MAC addresses on each port using the switchport port-security maximum command.
- Optionally, configure other port security features such as sticky MAC addresses using the switchport port-security mac-address sticky command.
- Ensure that all ports on the switch are configured with port security using the switchport port-security command.

### Configuration of Computers and Printers:
- Click on each computer and printer to access their configuration panels.
- Assign IP addresses, subnet masks, default gateways, and DNS servers to each device.
  - Default gateway for PC0 & PC1 <br/> <img src="https://github.com/0xbythesecond/Create-Simple-Network/assets/23303634/cff207b9-c931-41e3-93a3-8e6d3b1698c5" width="500" alt="configure ip address pc0"/>
  - With PC0 selected, choose Desktop and then choose IP Configuration <img src="https://github.com/0xbythesecond/Create-Simple-Network/assets/23303634/3a070c76-a59d-46da-afb5-12e2c71da7f9" width="500" alt="configure ip address pc0 step 1"/>
- Use IP addresses within the same subnet as the corresponding router interface.
  - PC0 (192.168.0.2), PC1 (192.168.03) & Printer0 (192.168.0.4) each with a subnet mask of 255.255.255.128
  -  <img src="https://github.com/0xbythesecond/Create-Simple-Network/assets/23303634/54e94dde-5097-4c7f-bb3e-445be6f22916" width="500" alt="configure ip address pc0 step 2"/>
    - <img src="https://github.com/0xbythesecond/Create-Simple-Network/assets/23303634/5af01582-7c38-4685-8e66-5892dcfff261" width="500" alt="printer0 ip address"/>
    - <img src="https://github.com/0xbythesecond/Create-Simple-Network/assets/23303634/a9a23b61-e7bb-4900-ad7c-c2c58ab5e1a9" width="500" alt="printer0 default gateway"/>

  - PC2 (192.168.0.130
- Optionally, configure static MAC addresses on the computers and printers to ensure compatibility with port security.

###  Testing Connectivity:
- Return to the simulation mode in Packet Tracer.
- Power on all devices.
-  Test connectivity between computers and printers on both sides of the router using the `ping` command.
- Attempt to connect unauthorized devices to switch ports to verify that port security is functioning as expected.

### Reflection:
- Reflect on the process of setting up the network.
- Consider any challenges encountered and how they were resolved.
- Evaluate the effectiveness of the network design and the implementation of port security in ensuring network security.

### Documentation:
- Document the network configuration, including IP addresses, router settings, switch configurations, and device connections.
- Include any troubleshooting steps taken and their outcomes.

### Conclusion:
- The completed network should demonstrate successful communication between devices on each side of the router, with port security enabled on the switch to enhance network security.
- The documentation serves as a reference for future network setups and troubleshooting.

