To enable SSH (Secure Shell) on a Cisco switch, follow these steps using the command-line interface (CLI):

1. Access Privileged EXEC Mode: Connect to the switch using a console cable and terminal emulation software. Enter the following command and press Enter:

   ```
   enable
   ```

2. Enter Global Configuration Mode: Enter global configuration mode by typing the following command and pressing Enter:

   ```
   configure terminal
   ```

3. Generate Encryption Keys (Optional): If encryption is desired for SSH sessions, generate encryption keys using the following command:

   ```
   crypto key generate rsa
   ```

   You will be prompted to choose the key modulus size. The recommended size is 1024 bits.

4. Enable SSH: To enable SSH on the switch, use the following command:

   ```
   ip ssh version 2
   ```

   This command enables SSH version 2 on the switch.

5. Set SSH Authentication: Specify the authentication method for SSH login. You can use local authentication or an external authentication server. To use local authentication, enter the following command:

   ```
   ip ssh authentication-retries <number>
   ```

   Replace `<number>` with the desired number of authentication retries before SSH access is denied.

6. Configure VTY Lines for SSH: Configure the virtual terminal (VTY) lines on the switch to allow SSH connections. Use the following command:

   ```
   line vty 0 15
   ```

7. Set SSH Transport Input: Specify that SSH is the only allowed transport input method for the VTY lines. Enter the following command:

   ```
   transport input ssh
   ```

8. Set VTY Line Authentication: Set a password for the VTY lines. Use the following command to set the password:

   ```
   password <password>
   ```

   Replace `<password>` with the desired password for SSH access.

9. Save Configuration: After configuring SSH, save the configuration changes. Enter the following command to exit the interface configuration mode:

   ```
   end
   ```

   Then, save the configuration to the startup configuration file using the following command:

   ```
   write memory
   ```

That's it! You have successfully enabled SSH on the Cisco switch. Now, you can remotely access the switch using SSH by establishing an SSH session from a computer or another network device. Remember to secure your SSH access by using strong passwords, limiting access to authorized users, and considering additional security measures, such as configuring SSH timeout settings or implementing access control lists (ACLs).
