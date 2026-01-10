# *NIX

## Linux Network Commands:
Command                                      | Description
-------------------------------------------- | ------------------------
watch ss -tp                                 | Network connections
netstat -ant                                 | Tcp connections
netstat -anu                                 | Udp connections
netstat -tulpn                               | Connetions with PIDs
lsof -i                                      | Established connections
smb://<ip>/share                             | Access windows smb share
share user x.x.x.x c$                        | Mount Windows share
smbclient -U user \\\\<ip>\\<share>          | SMB connect
ifconfig eth# <ip>/<cidr>                    | Set IP and netmask
ifconfig eth0:1 <ip>/<cidr>                  | Set virtual interface
route add default gw <gw_ip>                 | Set GW
ifconfig eth# mtu [size]                     | Change MTU size
export MAC=xx:xx:xx:xx:xx:xx                 | Change MAC
ifconfig <int> hw ether <MAC>                | Change MAC
macchanger -m <MAC> <int>                    | Backtrack MAC changer
iwlist <int> scan                            | Built-in wifi scanner
dig -x <ip>                                  | Domain lookup for IP
host <ip>                                    | Domain lookup for IP
host -t SRV _<service> tcp.url.com           | Domain SRV lookup
dig @<ip> domain -t AXFR                     | DNS Zone Xfer
host -l <domain> <namesvr>                   | DNS Zone Xfer
ip xfrm state list                           | Print existing VPN keys
ip addr add <ip>/<cird> dev eth0             | Adds `hidden' interface
/var/log/messages | grep DHCP                | List DHCP assignments
tcpkill host <ip> and port <port>            | Block ip:port
echo "1" > /proc/sys/net/ipv4/ip_forward     | Turn on IP Forwarding
echo "nameserver x.x.x.x" > /etc/resolv.conf | Add DNS Server

## Linux System Info
Command                                      | Description
-------------------------------------------- | ------------------------
nbtstat -A <ip>                              | Get hostname for <ip>
id                                           | Current username
w                                            | Logged on user
who -a                                       | User information
last -a                                      | Last users logged on
ps -ef                                       | Process listing (top)
df -h                                        | Disk usage (free)
uname -a                                     | Kernel version/CPU info
mount                                        | Mounted file systems
getent passwd                                | Show list of users
PATH=$PATH:/home/mypath                      | Add to PATH variable
kill <pid>                                   | kills process with <pid>
cat /etc/issue                               | Show OS info
cat /etc/*release*                           | Show OS version info
cat /proc/version                            | Show kernel info
rpm --query -all                             | Installed pkgs (Redhat)
rpm -ivh *.rpm                               | Install RPM (-e=remove)
dpkg -get-selections                         | Installed pkgs (Ubuntu)
dpkg -I *.deb                                | Install DEB (-r=remove)
pkginfo                                      | Installed pkgs (Solaris)
which <tscsh/csh/ksh/bash>                   | Show location of executable
chmod 750 <tcsh/csh/ksh>                     | Disable <shell>, force bash

## Linux Utility Commands
Command                                      | Description
-------------------------------------------- | ------------------------
wget http://<url> -O url.txt -o /dev/null    | Grab url
rdesktop <ip>                                | Remote Desktop to <ip>
scp /tmp/file user@x.x.x.x:/tmp/file         | Put file