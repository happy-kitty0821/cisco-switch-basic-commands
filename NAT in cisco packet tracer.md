
In Cisco Packet Tracer, Network Address Translation (NAT) allows you to translate private IP addresses to public IP addresses, enabling devices with private addresses to access the internet. Here's how you can configure NAT in Packet Tracer:

1. Open Packet Tracer and create a network topology with at least one router and one or more devices.

2. Access the CLI (Command Line Interface) of the router by clicking on it and selecting "CLI" from the menu.

3. Enter privileged EXEC mode by typing:
   ```
   enable
   ```

4. Enter global configuration mode by typing:
   ```
   configure terminal
   ```

5. Configure the interface facing the private network. For example, if the interface is FastEthernet0/0, type:
   ```
   interface FastEthernet0/0
   ```

6. Assign an IP address and subnet mask to the interface. For example:
   ```
   ip address 192.168.1.1 255.255.255.0
   ```

7. Enable NAT on the interface:
   ```
   ip nat inside
   ```

8. Configure the interface facing the public network. For example, if the interface is FastEthernet0/1, type:
   ```
   interface FastEthernet0/1
   ```

9. Assign an IP address and subnet mask to the interface. This IP address will be the public IP address assigned to your network by your ISP:
   ```
   ip address <public_IP_address> <subnet_mask>
   ```

10. Enable NAT on the interface:
    ```
    ip nat outside
    ```

11. Create an access control list (ACL) to define the traffic to be translated. For example, to translate all traffic from the private network to the public network, you can create an ACL allowing all IP traffic:
    ```
    access-list 1 permit any
    ```

12. Configure NAT translation using the ACL created. Specify the inside and outside interfaces:
    ```
    ip nat inside source list 1 interface FastEthernet0/1 overload
    ```

   This command specifies that traffic matching the ACL will be translated and sent out through the specified outside interface.

13. Exit the interface configuration mode by typing:
    ```
    exit
    ```

14. Save the configuration by typing:
    ```
    copy running-config startup-config
    ```

   This command saves the current configuration to be used on future restarts.

By following these steps, you can configure NAT in Cisco Packet Tracer to allow devices with private IP addresses to access the internet using a public IP address. Remember to adapt the commands to match your specific network topology and IP addressing scheme.

Please note that the specific commands and steps may vary depending on the router model and version of Packet Tracer you are using.
