Firewall Configuration Practical (Windows)
Objective

Configure and test basic firewall rules on Windows to allow or block traffic.

Steps
1. Open Firewall Configuration Tool

Open Control Panel → System and Security → Windows Defender Firewall

Or open PowerShell/Command Prompt with administrator rights

2. List Current Firewall Rules
netsh advfirewall firewall show rule name=all


This command displays all configured firewall rules (inbound and outbound).

3. Add a Rule to Block Inbound Traffic on Port 23 (Telnet)
netsh advfirewall firewall add rule name="Block Telnet" dir=in action=block protocol=TCP localport=23


This creates an inbound rule that blocks TCP traffic on port 23.

4. Test the Rule
telnet localhost 23


If the rule is active, the connection attempt will fail.

5. Remove the Test Block Rule
netsh advfirewall firewall delete rule name="Block Telnet"


This deletes the firewall rule and restores the system to its original state.

GUI Alternative

These actions can also be done through the Windows Firewall GUI:

Go to Advanced Settings → Inbound Rules → New Rule to add a block.

Right-click on the rule and select Delete to remove it.

Summary

A firewall filters network traffic based on predefined rules. In this practical, we:

Listed current rules.

Created a new inbound block rule for Telnet (port 23).

Tested the rule using Telnet.

Removed the rule to restore normal operation.

This demonstrates how Windows Firewall can be used to control traffic and improve security by blocking unsafe services while allowing trusted ones.
