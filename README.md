# WindowsOS-Security-Checklist - Lab Exercise

The purpose of this exercise is to develop a framework, baseline, and applying it to secure your windows operating systems. This checklist will exercise your ability to review different aspects of system configurations, processes, and network connectivity to protect your assests and data. 


1. <b>Keep the operating system up to date with the latest security patches and updates.</b>
    - Open Powershell and run the following scripts: 
      - Get-ComputerInfo | Select-Object WindowsProductName, WindowsInstallationType, WindowsVersion
      - Alternative: Get-WmiObject -Class Win32_OperatingSystem | Select-Object Caption, Version
    - This allows you to retreive your devices' current OS version

2. <b>Disable unnecessary services and protocols.</b>
    - Open the Windows Services app: Type "services.msc" into the Start menu search bar and select "Services" from the results.
    - Identify unnecessary services: Scroll through the list of services and identify those that you don't need. You can find information about each service by right-clicking it and selecting "Properties".
    - Disable unnecessary services: To disable a service, right-click it and select "Properties". Change the "Startup type" to "Disabled" and click "OK". Note that some services may be required by other software, so be careful not to disable any services that are critical for your system.
    - Disable unnecessary protocols: Open the Windows Network and Sharing Center by typing "ncpa.cpl" into the Start menu search bar and selecting "Network and Sharing Center" from the results. Click on your network connection and select "Properties". Uncheck any protocols that you don't need, such as "Client for Microsoft Networks" or "File and Printer Sharing for Microsoft Networks".
    - Reboot your computer: After making changes to services and protocols, it's a good idea to reboot your computer to ensure that the changes take effect.

3. <b>Configure a firewall to restrict incoming and outgoing traffic.</b>
    - Open the Windows Defender Firewall: Type "Windows Defender Firewall" into the Start menu search bar and select "Windows Defender Firewall with Advanced Security" from the results.
    - Create a new inbound rule: In the left-hand pane, click "Inbound Rules" and then click "New Rule" in the right-hand pane. Select the "Custom" option and click "Next". Choose the type of traffic to be restricted (e.g., TCP or UDP), and then specify the ports or range of ports to be restricted. Select "Block the connection" as the action to take when the rule applies, and click "Next".
    - Create a new outbound rule: In the left-hand pane, click "Outbound Rules" and then click "New Rule" in the right-hand pane. Follow the same steps as for the inbound rule to create a new outbound rule.
    - Apply the rules: Once you have created the inbound and outbound rules, apply them by clicking "Finish". The new rules will take effect immediately.

4. Use strong passwords and implement password policies.

5. Limit user privileges.

6. Configure antivirus and anti-malware software.

7. Encrypt sensitive data.

8. Enable auditing and logging.

9. Disable unnecessary remote access.

10. Regularly perform backups.

11. Enable BitLocker or other encryption software to encrypt the system drive.

12. Enable Windows Defender or another antivirus software and keep it updated.

13. Disable Autorun and Autoplay features to prevent malware infections from USB devices.

14. Configure User Account Control (UAC) to the highest level.

15. Disable unnecessary system services such as Bluetooth, Print Spooler, and Remote Registry.

16. Set strong password policies, including password complexity and regular password changes.

17. Disable unused network protocols such as NetBIOS and SMBv1.

18. Disable unused user accounts and rename the default Administrator account.

19. Configure Group Policy settings to restrict access to sensitive areas such as the registry, file system, and system settings.

20. Configure Windows Firewall to block incoming and outgoing traffic except for authorized applications and services.

21. Implement two-factor authentication for privileged accounts.

22. Disable unnecessary startup programs and services.

23. Enable DEP (Data Execution Prevention) to protect against memory-based attacks.

24. Enable SEHOP (Structured Exception Handler Overwrite Protection) to protect against SEH-based attacks.

25. Configure Event Log settings to retain logs for a sufficient period and protect logs from unauthorized access.

By following this checklist, a Windows operating system can be hardened to reduce the risk of security incidents and protect sensitive data from unauthorized access. It's important to note that this is not an exhaustive list and that additional steps may be required based on the specific environment and security requirements.
