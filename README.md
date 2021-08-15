# Windows Subsystem for Linux Documentation

Follow this link: [link to docs!](https://docs.microsoft.com/en-us/windows/wsl/)

## Step 1 - Enable the Windows Subsystem for Linux (PowerShell)

```bash
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```
## Step 2 - Check requirements for running WSL 2
To update to WSL 2, you must be running Windows 10.

For x64 systems: Version 1903 or higher, with Build 18362 or higher.
For ARM64 systems: Version 2004 or higher, with Build 19041 or higher.
Builds lower than 18362 do not support WSL 2. Use the Windows Update Assistant to update your version of Windows.
To check your version and build number, select Windows logo key + R, type winver, select OK. Update to the latest Windows version in the Settings menu.

## Step 3 - Enable Virtual Machine feature
Open PowerShell as Administrator and run:
```bash
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
bash
Restart your machine to complete the WSL install and update to WSL 2.
