# 3630

Currently running Ubuntu 26

Figuring out RDP and SSH
----------------------------------------------------------------------------------------------------------------------------------------------------------------------
To enable remote access on Ubuntu (using built-in RDP desktop sharing or remote login), follow the steps in Share your desktop remotely - Ubuntu Desktop documentation:

Enable Remote Desktop via Settings

1. Open Settings from the application menu or top-right system tray.
2. Click on System in the left sidebar, then select Remote Desktop.
3. Choose your preferred connection mode:
	• Desktop Sharing: Lets someone view or control your active desktop while you are logged in.
	• Remote Login: Lets you log into your user account from a remote computer (you must be logged out of the physical session first, or it will terminate the running session).
4. Click Unlock (if prompted) and enter your Ubuntu administrative password.
5. Toggle on Desktop Sharing / Remote Control or Remote Login.
6. Note down the automatically assigned username, password, and port number (typically 3389 for Remote Login and 3390 if both are enabled).

Configure the Firewall (if needed)

Ensure your firewall allows incoming RDP traffic on the active port (such as port 3389) by running this command in your terminal:
bash
sudo ufw allow 3389
Use code with caution.

Connect from a Client

• Use an RDP-compatible client like the built-in Remote Desktop app on Windows or Remmina on Ubuntu.
• Enter the server's IP address, port number (e.g., 192.168.1.X:3389), and the remote username and password from your Remote Desktop settings.
------------------------------------------------------------------------------------------------------------------------------------------------

