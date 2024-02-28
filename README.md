# Create Simple Network
![Simple Network(1)](https://github.com/0xbythesecond/Create-Simple-Network/assets/23303634/bd9cb0cb-af62-46f1-9b31-ce8d3966be1e)



## Objective:
The objective of this lab is to configure a simple network with multiple devices connected through a router and switches.

### Topology Setup:
- Open Packet Tracer and select the router, one switch, four computers, and two printers.
- Drag and drop the devices onto the workspace.
- Connect one switch to each side of the router using Ethernet cables.
- Connect two computers and 1 printer to each switch.

<p align=center><img src="https://github.com/0xbythesecond/Create-Simple-Network/assets/23303634/0bef1a0e-d3f6-4879-bdc9-81a0d8386f96" width="800" alt="packet tracer setup"/></p>


### Configuration of Router Interfaces:
- Access the router's Command Line Interface (CLI) by clicking on it and selecting "Command Line Interface."
       
<p align=center><img src="https://github.com/0xbythesecond/Create-Simple-Network/assets/23303634/7e6e93dd-8834-4ce9-9abe-c23456220523" width="500" alt="select router cli"/>

- First you will be prompted with 
- Enter global configuration mode initially by using the `enable` (privileged EXEC mode) command and then to enter the global configuration mode by entering `configure terminal` or `conf t` for short.
- Configure IP addresses for each router interface using the interface and ip address commands.
- For example, interface gigabitethernet0/0 followed by ip address 192.168.1.1 255.255.255.0.

### Configuration of Switch (with Port Security):
- Click on the switch to access its configuration panel.
- Enable port security on the switch by setting the maximum number of allowed MAC addresses on each port using the switchport port-security maximum command.
- Optionally, configure other port security features such as sticky MAC addresses using the switchport port-security mac-address sticky command.
- Ensure that all ports on the switch are configured with port security using the switchport port-security command.

### Configuration of Computers and Printers:
- Click on each computer and printer to access their configuration panels.
- Assign IP addresses, subnet masks, default gateways, and DNS servers to each device.
- Use IP addresses within the same subnet as the corresponding router interface.
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

