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
```
Restart your machine to complete the WSL install and update to WSL 2.

## Step 4 - Download the Linux kernel update package
[WSL2 Linux kernel update package for x64 machines](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi)

## Step 5 - Set WSL 2 as your default version
```bash
wsl --set-default-version 2
```

## Step 6 - Install your Linux distribution of choice
Ubuntu
[Ubuntu 18.04](https://www.microsoft.com/store/apps/9N9TNGVNDL3Q)

The first time you launch a newly installed Linux distribution, a console window will open and you'll be asked to wait for a minute or two for files to de-compress and be stored on your PC. All future launches should take less than a second.

You will then need to create a user account and password for your new Linux distribution.

## Common command
[Follow this link:](https://docs.microsoft.com/en-us/windows/wsl/wsl-config)

```
wslconfig /?
wslconfig /list
wsl --unregister Ubuntu
```

## Accessing Linux files from Windows using \\wsl$
Accessing Linux files via \\wsl$ will use the default user of your WSL distribution. Therefore any Windows app accessing Linux files will have the same permissions as the default user.

## Configure global options with .wslconfig
Available in Windows Build 19041 and later

You can configure global WSL options by placing a .wslconfig file into the root directory of your users folder: C:\Users\<yourUserName>\.wslconfig. Many of these files are related to WSL 2, please keep in mind you may need to run wsl --shutdown to shut down the WSL 2 VM and then restart your WSL instance for these changes to take affect.

Here is a sample .wslconfig file:
```
[wsl2]
kernel=C:\\temp\\myCustomKernel
memory=4GB # Limits VM memory in WSL 2 to 4 GB
processors=2 # Makes the WSL 2 VM use two virtual processors
```
