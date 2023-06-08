DHCP (Dynamic Host Configuration Protocol) allows devices on a network to automatically obtain IP addresses and network configuration settings. Although DHCP is typically associated with routers or dedicated DHCP servers, some Cisco switches also support DHCP functionality. Here's a simplified explanation of how to configure DHCP on a Cisco switch:

1. Access Privileged EXEC Mode: Connect to the switch using a console cable and terminal emulation software. Enter the following command and press Enter:
   
   ```
   enable
   ```

2. Enter Global Configuration Mode: Enter global configuration mode by typing the following command and pressing Enter:

   ```
   configure terminal
   ```

3. Enable DHCP Service: To enable the DHCP service on the switch, use the following command:

   ```
   ip dhcp excluded-address <start-ip> <end-ip>
   ```

   Replace `<start-ip>` and `<end-ip>` with the range of IP addresses you want to exclude from the DHCP pool. These addresses should be reserved for static assignment.

4. Create DHCP Pool: Configure a DHCP pool on the switch to specify the range of IP addresses available for dynamic assignment. Use the following command:

   ```
   ip dhcp pool <pool-name>
   ```

   Replace `<pool-name>` with a name for the DHCP pool.

5. Specify Network Parameters: Set the network parameters for the DHCP pool, including the network subnet, default gateway, and DNS server(s). Use the following commands:

   ```
   network <network-subnet> <subnet-mask>
   default-router <default-gateway>
   dns-server <dns-server-ip>
   ```

   Replace `<network-subnet>` with the network subnet address, `<subnet-mask>` with the subnet mask, `<default-gateway>` with the default gateway IP address, and `<dns-server-ip>` with the IP address of the DNS server(s).

6. Configure Lease Duration (Optional): You can set a lease duration for the DHCP addresses assigned by the switch. By default, the lease duration is 1 day. If you want to modify it, use the following command:

   ```
   lease <lease-duration>
   ```

   Replace `<lease-duration>` with the desired lease duration in days, hours, or minutes (e.g., 1 day, 8 hours, 3600 seconds).

7. Save Configuration: After configuring DHCP, save the configuration changes. Enter the following command to exit the interface configuration mode:

   ```
   end
   ```

   Then, save the configuration to the startup configuration file using the following command:

   ```
   write memory
   ```

That's it! You have successfully configured DHCP on the Cisco switch. Now, the switch will dynamically assign IP addresses and network configuration settings to devices connected to the network.
