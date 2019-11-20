Install SAMBA Server (SMBD) to share directories on your Pi with Windows clients.

See https://www.raspberrypi.org/forums/viewtopic.php?t=214546

Step by step:

sudo apt-get update
sudo apt-get install samba
note: package isc-dhcp-client is already installed; this helps samba register host name in any WINS service identified by DHCP.

cd /etc/samba
sudo vi smb.conf
add this to bottom of /etc/samba/smb.conf:


[PIFILES]
path = /var/samba/shared
guest ok = yes
read only = no
sudo mkdir /var/samba
sudo mkdir /var/samba/shared
sudo chmod a+w /var/samba/shared

And restart the service:

sudo systemctl restart smbd

At this time, I could browse network in Windows 10 explorer and see my Raspberry pi host; I could map a drive letter to \\raspberrypi\pifiles, and I could add and remove files and directories there.  Consult SAMBA configuration resources to go further, for instance to secure access or manage file ownership.

