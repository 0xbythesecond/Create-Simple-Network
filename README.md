# Create Simple Network


Objective: Create a simple network that consist of two computers and a printer on each side of the router within Packet Tracer

Step 1: Design the Network Topology
        Open Packet Tracer and select a router from the available devices.
        Drag the router onto the workspace.
        Connect two computers and a printer to each side of the router using appropriate cables.

Step 2: Assign IP Addresses
        For each device, click on it to access its configuration panel.
        In the configuration panel, navigate to the "Desktop" tab.
        Assign IP addresses to each device. For instance, use 192.168.1.1 for the first computer, 192.168.1.2 for the printer, and so on.

Step 3: Configure Router Interfaces
        Access the router's command-line interface (CLI) by clicking on it.
        Enter global configuration mode using the enable command and configure the router's interfaces with IP addresses.
        For example, use interface gig0/0 and ip address 192.168.1.254 for the interface connected to the first set of devices.

Step 4: Set Up Static Routing
        In the router's CLI, enter global configuration mode.
        Use the ip route command to configure static routes. For instance, ip route 192.168.2.0 255.255.255.0 192.168.1.254 to route traffic from one network to the other.

Step 5: Test Connectivity
        Return to the simulation mode in Packet Tracer.
        Open the command prompt or terminal for each device.
        Ping devices on the opposite side of the router to verify connectivity.

Step 6: Implement Basic Security
        Still in the router's CLI, set passwords for security.
        Use commands like enable secret and enable password to secure privileged and user EXEC modes.

Reflection:
        Evaluate the effectiveness of the network design in terms of connectivity and security.
        Consider any challenges faced during the configuration and how they were resolved.

Step 7: Documentation
   - Create a document detailing the network configuration.
   - Include IP addresses, router settings, and any security measures implemented.

Step 8: Save and Share
   - Save the Packet Tracer file for future reference or sharing.
   - Share the file with others for review or collaboration.

Objective Review:
  - Confirm that devices on different sides of the router can communicate successfully.
  - Check that security measures are in place and effective for the network's purpose.

    Final Reflection:

    Reflect on the overall experience, considering the success of the network setup, any lessons learned, and improvements for future designs.

    Conclusion:

    The completed network should showcase functional connectivity between devices on different sides of the router, with documented 

    configurations and basic security measures in place.

