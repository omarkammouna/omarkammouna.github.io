
#  Wsl2 Ubuntu Setup

Follow these steps to set up WSL2 with Ubuntu on Windows:

1. **Enable WSL2**
   - Open PowerShell as an administrator.
   - Run the command: `wsl --install`.
   - Wait for the installation to complete.

2. **Install Ubuntu**
   - Open Microsoft Store.
   - Search for "Ubuntu" and select the latest version.
   - Click "Install" and wait for the installation to finish.

3. **Launch Ubuntu**
   - Open the Start menu and find Ubuntu in the app list.
   - Click on Ubuntu to launch it for the first time.
   - Set up your username and password when prompted.

4. **Update Ubuntu**
   - Launch the Ubuntu terminal.
   - Run the following commands:
     ```
     sudo apt update
     sudo apt upgrade -y
     ```

5. **WSL2 Configuration**
   - Open PowerShell as an administrator.
   - Run the command: `wsl --set-version <Distro> 2`, replacing `<Distro>` with the name of your installed Ubuntu distribution.

6. **Set Ubuntu as the Default WSL Distro**
   - Open PowerShell as an administrator.
   - Run the command: `wsl --set-default <Distro>`, replacing `<Distro>` with the name of your installed Ubuntu distribution.

Congratulations! You have successfully set up WSL2 Ubuntu on your Windows machine.

> Note: Remember to consult the official Microsoft documentation for any specific updates or changes to the setup process.
