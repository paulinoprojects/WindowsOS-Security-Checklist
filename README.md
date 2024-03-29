# WindowsOS-Security-Checklist - Lab Exercise

The purpose of this exercise is to analyze and defend your windows operating systems. This checklist will exercise your ability to review different aspects of system configurations, processes, and network connectivity to protect your assests and data. 


1. <b>Keep the operating system up to date with the latest security patches and updates.</b>
    - Open Powershell and run the following scripts: 
      - Get-ComputerInfo | Select-Object WindowsProductName, WindowsInstallationType, WindowsVersion
      - Alternative: Get-WmiObject -Class Win32_OperatingSystem | Select-Object Caption, Version
    - This allows you to retreive your devices' current OS version and determine if an update is needed.

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

4. <b>Use strong passwords and implement password policies.</b>
    - Open the Group Policy Editor: Type "gpedit.msc" into the Start menu search bar and select "Edit group policy" from the results.
    - Navigate to the Password Policy settings: In the left-hand pane, navigate to "Computer Configuration" > "Windows Settings" > "Security Settings" > "Account Policies" > "Password Policy".
    - Configure the password policy settings: In the right-hand pane, you can configure various password policy settings, such as the minimum password length, complexity requirements, and password expiration policies. Set these policies according to your organization's security requirements.
    - Apply the password policy settings: Once you have configured the password policy settings, close the Group Policy Editor and restart your computer for the changes to take effect.

5. <b>Limit user privileges.</b>
    - Create a standard user account: By default, Windows creates a user account with administrative privileges. However, you can create a standard user account for everyday use. To do this, go to "Settings" > "Accounts" > "Family & other people", and click "Add someone else to this PC". Then, choose "I don't have this person's sign-in information" and follow the prompts to create a new standard user account.
    - Remove administrative privileges: Once you have created a standard user account, you can remove administrative privileges from other user accounts. To do this, go to "Settings" > "Accounts" > "Family & other people", and select the user account you want to modify. Then, click "Change account type" and select "Standard user".
    - Use the UAC feature: The User Account Control (UAC) feature in Windows can help to prevent unauthorized changes by requiring administrative approval for certain actions. To enable UAC, go to "Settings" > "Update & Security" > "Windows Security" > "Virus & threat protection" > "Manage settings", and turn on "Tamper Protection". Then, go to "Settings" > "Accounts" > "Sign-in options" and turn on "User Account Control".

6. <b>Configure antivirus and anti-malware software.</b>
    - Install antivirus and anti-malware software: There are many antivirus and anti-malware software options available for Windows, such as Windows Defender, McAfee, Norton, and Avast. Choose one and install it on your system.
    - Update the antivirus and anti-malware software: Once you have installed the software, make sure to update it regularly to ensure it has the latest virus definitions and malware signatures. Most antivirus and anti-malware software programs provide an option to update automatically.
    - Configure the antivirus and anti-malware software settings: Most antivirus and anti-malware software programs have default settings that provide basic protection. However, you can customize the settings to meet your specific needs. For example, you can configure the software to scan for threats on a regular basis, enable real-time protection, and set up alerts for potential threats.
    - Perform regular scans: Even with real-time protection enabled, it's still a good idea to perform regular scans of your system to check for any hidden threats. Schedule regular scans at a time when your computer is not in use, such as overnight.

7. <b>Encrypt sensitive data.</b>
    - Choose the encryption method: Windows provides two methods for encrypting data - BitLocker and Encrypting File System (EFS). BitLocker is a full-disk encryption tool that encrypts the entire hard drive, while EFS is a file-level encryption tool that encrypts individual files or folders.
    - Enable BitLocker or EFS: To enable BitLocker, go to "Control Panel" > "System and Security" > "BitLocker Drive Encryption", and follow the prompts to encrypt your hard drive. To enable EFS, right-click on the file or folder you want to encrypt, select "Properties", and then click on the "Advanced" button. Check the box next to "Encrypt contents to secure data" and click "OK".
    - Create a strong password: To encrypt the data, you'll need to create a strong password that will be required to access the data. Use a combination of uppercase and lowercase letters, numbers, and symbols, and avoid using easily guessable information like birthdates or names.
    - Backup your recovery key: In case you forget your password, Windows will provide a recovery key that you can use to unlock the encrypted data. Make sure to backup this key to a safe location, such as a USB drive or a cloud storage service.

8. <b>Enable auditing and logging.</b>
    - Open the Local Security Policy: Go to "Control Panel" > "Administrative Tools" > "Local Security Policy".
    - Enable auditing policies: In the Local Security Policy window, go to "Local Policies" > "Audit Policy". Here you can configure the auditing policies for various events, such as account logon events, object access, and policy changes. Select the events you want to audit and click "OK".
    - Configure logging options: To configure logging options, go to "Control Panel" > "Administrative Tools" > "Event Viewer". Here you can view the logs for various system events, such as application events, security events, and system events. To configure the logging options, right-click on the log you want to configure and select "Properties". Here you can specify the maximum log size, overwrite options, and event filter options.
    - Monitor and review the logs: Once auditing and logging are enabled, you can monitor and review the logs on a regular basis to identify any security-related incidents or user activity. Use the Event Viewer to view the logs and filter them by event type, date, and source.

9. <b>Disable unnecessary remote access.</b>
    - Disable Remote Desktop: Remote Desktop is a built-in feature in Windows that allows users to access your computer remotely. If you don't need this feature, you can disable it to prevent unauthorized access. To disable Remote Desktop, go to "Control Panel" > "System" > "Remote settings", and uncheck the box next to "Allow Remote Assistance connections to this computer".
    - Disable Remote Assistance: Remote Assistance is another feature that allows someone else to remotely control your computer. To disable this feature, go to "Control Panel" > "System" > "Remote settings", and uncheck the box next to "Allow Remote Assistance connections to this computer".
    - Disable Remote Registry: Remote Registry is a feature that allows remote users to access and modify the Windows Registry on your computer. To disable this feature, go to "Control Panel" > "Administrative Tools" > "Services", and locate the "Remote Registry" service. Right-click on it and select "Properties", and set the "Startup type" to "Disabled".
    - Disable other remote access tools: If you have other third-party remote access tools installed on your system, such as TeamViewer or LogMeIn, make sure to disable them if you don't need them.

10. <b>Regularly perform backups.</b>
    - Choose a backup method: Windows provides several built-in backup methods, such as File History, Backup and Restore, and System Image Backup. Choose the backup method that best fits your needs based on the type of data you want to backup and the level of protection you need.
    - Set up the backup schedule: Once you have chosen a backup method, set up a backup schedule to ensure that your data is backed up regularly. You can choose to backup your data daily, weekly, or monthly, depending on your needs.
    - Select the backup location: Choose a backup location that is safe and secure, such as an external hard drive, a network location, or a cloud storage service. Make sure to choose a location that is separate from your main system drive to protect your data in case of a system failure.
    - Start the backup: Once you have set up the backup schedule and selected the backup location, start the backup process. Depending on the backup method you are using, this may involve selecting the files or folders you want to backup, choosing the backup location, and configuring any additional backup settings.
    - Monitor the backup process: Once the backup process is started, monitor the backup progress to ensure that it is completed successfully. Check the backup logs and notifications to identify any errors or issues that may require attention.

11. <b>Disable Autorun and Autoplay features to prevent malware infections from USB devices.</b>
    - Open the Control Panel: Click the Start button and select Control Panel.
    - Open AutoPlay: Click on "Hardware and Sound" and then click on "AutoPlay".
    - Disable AutoPlay: In the AutoPlay settings window, uncheck the box next to "Use AutoPlay for all media and devices".
    - Disable Autorun: Open the Registry Editor by pressing the Windows key + R, typing "regedit" and pressing Enter. Navigate to the following key in the Registry Editor: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\Explorer
    - Create a new DWORD value: Right-click in the right-hand pane and select "New" > "DWORD Value". Name the new value "NoDriveTypeAutoRun".
    - Set the value data: Double-click on the new value you just created and set the "Value data" to "0xFF" (without the quotes).
    - Close the Registry Editor: Close the Registry Editor and restart your computer.
    - Note: Keep in mind that this will prevent the automatic execution of software and files on USB devices, so you will need to manually open files and programs on the device. If you need to use Autorun or Autoplay for a specific purpose, you can enable it again using the same steps above and setting the "Value data" to "0x91".

12. <b>Configure User Account Control (UAC) to the highest level.</b>
    - User Account Control (UAC) is a security feature in Windows that helps prevent unauthorized changes to your computer. By configuring UAC to the highest level, you can ensure that only authorized users can make changes to your computer. Here are the steps to configure UAC to the highest level on Windows:
        - Open the Control Panel: Click the Start button and select Control Panel.
        - Open User Accounts: Click on "User Accounts and Family Safety" and then click on "User Accounts".
        - Change UAC settings: Click on "Change User Account Control settings" and move the slider to the highest level, which is "Always notify".
        - Click OK: Click on "OK" to save the changes.
        - Restart your computer: Restart your computer for the changes to take effect.

13. <b>Disable unused user accounts and rename the default Administrator account.</b>
    - Open the Computer Management tool: Press the Windows key + X and select "Computer Management" from the menu.
    - Navigate to the User Accounts section: Click on "Local Users and Groups" in the left-hand menu and then click on "Users".
    - Disable unused user accounts: Right-click on any user accounts that are no longer needed and select "Properties". Check the box next to "Account is disabled" and click "OK" to disable the account.
    - Rename the default Administrator account: Right-click on the default Administrator account and select "Rename". Choose a new name for the account and click "OK".
    - Set a strong password for the Administrator account: Right-click on the renamed Administrator account and select "Set Password". Choose a strong password for the account and click "OK".
    - Log out of the Administrator account: Log out of the Administrator account and log in using a standard user account.

14. <b>Configure Group Policy settings to restrict access to sensitive areas such as the registry, file system, and system settings.</b>
    - Open the Group Policy Editor: Press the Windows key + R, type "gpedit.msc" and press Enter.
    - Navigate to the security settings: Expand "Local Computer Policy" and navigate to "Computer Configuration" > "Windows Settings" > "Security Settings".
    - Configure the security settings: Right-click on "Registry", "File System", or "System" and select "Add User or Group". Add the user or group you want to restrict access for and click "OK".
    - Configure the permissions: Right-click on the user or group you just added and select "Properties". Choose the level of access you want to allow for each user or group.
    - Save your changes: Click "OK" to save your changes.

15. <b>Implement two-factor authentication for privileged accounts.</b>
    - Choose a two-factor authentication solution: There are many third-party solutions available, such as Duo Security, RSA SecurID, and Microsoft Authenticator. Choose a solution that meets your organization's needs and requirements.
    - Install and configure the authentication solution: Follow the instructions provided by the vendor to install and configure the two-factor authentication solution on your Windows servers.
    - Configure privileged accounts for two-factor authentication: Once the authentication solution is installed and configured, you can configure your privileged accounts to require two-factor authentication. This can be done through Active Directory or through the authentication solution itself, depending on the solution you choose.
    - Test and monitor the authentication solution: Once the solution is configured, test it to ensure that it is working correctly. Monitor the solution to detect any issues or anomalies that may arise.

16. <b>Disable unnecessary startup programs and services.</b>
    - Open the Task Manager: You can do this by right-clicking on the taskbar and selecting "Task Manager" from the menu.
    - Go to the "Startup" tab: In the Task Manager, click on the "Startup" tab to see a list of all the programs that start automatically when your computer boots up.
    - Disable unnecessary startup programs: Review the list of startup programs and disable any that are unnecessary or that you don't recognize. To do this, select the program and click on the "Disable" button.
    - Open the Services app: Press the Windows key + R on your keyboard to open the Run dialog box, then type "services.msc" and press Enter.
    - Review the list of services: In the Services app, review the list of services that are running on your computer. Identify any services that are unnecessary or that you don't recognize.
    - Disable unnecessary services: To disable a service, right-click on it and select "Properties." Change the "Startup type" to "Disabled" and click on "Apply" and "OK."
    - Note: be careful not to disable any programs or services that are necessary for your computer to function properly. If you are unsure about a program or service, it's best to do some research before disabling it.

17. <b>Enable DEP (Data Execution Prevention) to protect against memory-based attacks.</b>
    - DEP (Data Execution Prevention) is a security feature in Windows that helps protect against memory-based attacks such as buffer overflows. Enabling DEP on your Windows computer can help improve security. Here are the steps to enable DEP:
        - Open the Control Panel: You can do this by clicking on the "Start" button and selecting "Control Panel" from the menu.
        - Go to System Properties: In the Control Panel, click on "System and Security" and then select "System." Alternatively, you can right-click on "Computer" and select "Properties."
        - Click on "Advanced system settings": In the System window, click on "Advanced system settings" on the left-hand side.
        - Go to the "Advanced" tab: In the System Properties window, click on the "Advanced" tab.
        - Click on "Settings" under "Performance": Under the "Performance" section, click on the "Settings" button.
        - Go to the "Data Execution Prevention" tab: In the Performance Options window, go to the "Data Execution Prevention" tab.
        - Enable DEP for essential Windows programs and services: Select the "Turn on DEP for essential Windows programs and services only" option.
        - Enable DEP for all programs and services: Alternatively, you can select the "Turn on DEP for all programs and services except those I select" option and add any programs that you want to exclude from DEP.
        - Click "Apply" and "OK": Click on the "Apply" button and then click on "OK" to save the changes.
        - Enabling DEP on your Windows computer can help improve security by protecting against memory-based attacks. However, some older programs may not be compatible with DEP, so you may need to adjust the settings or find an alternative solution if you experience any issues.

18. <b>Enable SEHOP (Structured Exception Handler Overwrite Protection) to protect against SEH-based attacks.</b>
    - SEHOP (Structured Exception Handler Overwrite Protection) is a security feature in Windows that helps to protect against Structured Exception Handler (SEH) overwrite attacks. To enable SEHOP on Windows, follow these steps:
        - Open the Start menu and search for "regedit" to open the Registry Editor.
        - Navigate to the following registry key: HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Session Manager\kernel
        - Right-click on an empty space in the right-hand pane and select "New" -> "DWORD Value".
        - Name the new DWORD value "DisableExceptionChainValidation".
        - Double-click on the new value and set its data to "0".
        - Close the Registry Editor and restart your computer.
        - After restarting your computer, SEHOP will be enabled and help to protect against SEH-based attacks. It is important to note that some software may be incompatible with SEHOP, so it is recommended to test the feature before enabling it in a production environment.

19. <b>Configure Event Log settings to retain logs for a sufficient period and protect logs from unauthorized access.</b>
    - Open the Event Viewer by searching for "event viewer" in the Start menu.
    - Click on "Windows Logs" in the left-hand pane and select the log that you want to configure (e.g., Security, Application, etc.).
    - Right-click on the log and select "Properties".
    - In the "Log Properties" window, click on the "General" tab.
    - Under "Log Size", select "Overwrite events as needed" or "Archive the log when full, do not overwrite events".
    - Under "Retention Method", select "Overwrite events older than [X] days" or "Archive the log when full, do not overwrite events".
    - Click on the "Security" tab and configure the appropriate access permissions for the log.
    - Click "OK" to save your changes.

By following this checklist, a Windows operating system can be hardened to reduce the risk of security incidents and protect sensitive data from unauthorized access. It's important to note that this is not an exhaustive list and that additional steps may be required based on the specific environment and security requirements.
