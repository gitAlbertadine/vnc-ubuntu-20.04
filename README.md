# vnc-ubuntu-20.04
The best vnc server
```
sudo dd if=/dev/zero of=/swapfile bs=16384 count=1048576
sudo chmod 600 /swapfile
sudo mkswap /swapfile
sudo swapon /swapfile
sudo sh -c 'echo "/swapfile swap swap defaults 0 0" >> /etc/fstab'
sudo sh -c 'echo "vm.swappiness=10" >> /etc/sysctl.conf'

sudo apt update
sudo apt install tasksel -y
sudo tasksel
sudo systemctl set-default graphical.target
sudo systemctl reboot
sudo apt install tigervnc-standalone-server tigervnc-common
vncpasswd
vncserver -localhost no
vncserver -list
vncserver -kill :1
sudo vim  ~/.vnc/xstartup
   #!/bin/sh
   xrdb $HOME/.Xresources
   vncconfig -iconic &
   dbus-launch --exit-with-session gnome-session &
sudo chmod u+x  ~/.vnc/xstartup 
sudo chmod 777 ~/.vnc/xstartup
vncserver
tigervncserver -xstartup /usr/bin/xterm
```
