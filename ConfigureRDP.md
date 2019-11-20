Raspbian includes a low-compatibility RealVNC server, which I have been unable to connect to, so I did the following:

sudo apt-get update
sudo apt-get upgrade
sudo apt-get autoremove
sudo apt-get remove realvnc-vnc-server
sudo apt-get purge realvnc-vnc-server
sudo apt-get install tightvncserver
sudo apt-get install xrdp

Now I was able to access my Pi server using Windows remote desktop.  VNC should work as well, but I get an actively refused error when I try, suggesting I need to lower security or manually share a public cert.  RDP works for me.

