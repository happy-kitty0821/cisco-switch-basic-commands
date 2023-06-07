Port security on a switch allows you to control which devices can connect to specific switch ports. By setting up port security, you can limit the number of devices or MAC addresses that are allowed to connect, thereby preventing unauthorized access to the network.

To configure port security on a Cisco switch, follow these steps using the command-line interface (CLI):

1. Access Privileged EXEC Mode: Connect to the switch using a console cable and terminal emulation software. Enter the following command and press Enter:

   ```
   enable
   ```

2. Enter Global Configuration Mode: Enter global configuration mode by typing the following command and pressing Enter:

   ```
   configure terminal
   ```

3. Select the Switch Port: Choose the specific switch port you want to configure for port security. For example, if you want to configure port security on interface GigabitEthernet1/0/1, enter the following command:

   ```
   interface GigabitEthernet1/0/1
   ```

4. Enable Port Security: To enable port security on the selected port, use the following command:

   ```
   switchport port-security
   ```

5. Set the Maximum Number of Allowed MAC Addresses: Determine the maximum number of MAC addresses you want to allow on the port. For example, to allow only one MAC address, use the following command:

   ```
   switchport port-security maximum 1
   ```

6. Configure Violation Actions: Decide what action the switch should take if a violation occurs, such as when an unauthorized device tries to connect. You can choose from the following actions:

   - Shutdown: The switch shuts down the port.
   - Restrict: The switch restricts the port but continues to allow traffic from the detected MAC addresses.
   - Protect: The switch restricts the port and discards traffic from the detected MAC addresses.
   
   To set the violation action to shutdown, use the following command:

   ```
   switchport port-security violation shutdown
   ```

7. (Optional) Specify Allowed MAC Addresses: If you want to specify specific MAC addresses that are allowed to connect to the port, use the following command for each MAC address:

   ```
   switchport port-security mac-address <mac-address>
   ```

   Replace `<mac-address>` with the desired MAC address. Repeat this command for each MAC address you want to allow.

8. Save Configuration: After configuring port security, save the configuration changes. Enter the following command to exit the interface configuration mode:

   ```
   end
   ```

   Then, save the configuration to the startup configuration file using the following command:

   ```
   write memory
   ```
Remember to adjust the commands based on the specific port and requirements of your network.
