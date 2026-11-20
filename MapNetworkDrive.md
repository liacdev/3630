Map a network drive in Windows 11 to the 3030 folder 'NetworkSaves'

Using Samba

-------------------------------------------------------------
To map a network drive in Windows 11 to an Ubuntu folder, share the folder from Ubuntu using Samba (SMB) and then map it as a drive letter in Windows 11 File Explorer.

1. Share the Folder on Ubuntu (Samba)

• Install Samba and enable the service:bash
sudo apt update && sudo apt install samba
sudo systemctl enable --now smbd
Use code with caution.
* Create or choose the folder you want to share (for example, `~/shared`) [0.6.4].
* Add a share block to `/etc/samba/smb.conf` [0.6.4, 0.6.7]:
  ```ini
  [shared]
     path = /home/YOUR_USERNAME/shared
     browsable = yes
     writable = yes
     guest ok = no
     read only = no
• Set a Samba password for your user and restart Samba:bash
sudo smbpasswd -a YOUR_USERNAME
sudo systemctl restart smbd
Use code with caution.
* Allow Samba through the firewall if UFW is active:
  ```bash
  sudo ufw allow samba
• Find your Ubuntu machine's IP address using ip a or hostname -I.
-------------------------------------------------------------------------------------------
