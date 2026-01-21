# *NIX

## Linux Network Commands:
Command                                                | Description
------------------------------------------------------ | ----------------------------------
watch ss -tp                                           | Network connections
netstat -ant                                           | Tcp connections
netstat -anu                                           | Udp connections
netstat -tulpn                                         | Connetions with PIDs
lsof -i                                                | Established connections
smb://<ip>/share                                       | Access windows smb share
share user x.x.x.x c$                                  | Mount Windows share
smbclient -U user \\\\<ip>\\<share>                    | SMB connect
ifconfig eth# <ip>/<cidr>                              | Set IP and netmask
ifconfig eth0:1 <ip>/<cidr>                            | Set virtual interface
route add default gw <gw_ip>                           | Set GW
ifconfig eth# mtu [size]                               | Change MTU size
export MAC=xx:xx:xx:xx:xx:xx                           | Change MAC
ifconfig <int> hw ether <MAC>                          | Change MAC
macchanger -m <MAC> <int>                              | Backtrack MAC changer
iwlist <int> scan                                      | Built-in wifi scanner
dig -x <ip>                                            | Domain lookup for IP
host <ip>                                              | Domain lookup for IP
host -t SRV _<service> tcp.url.com                     | Domain SRV lookup
dig @<ip> domain -t AXFR                               | DNS Zone Xfer
host -l <domain> <namesvr>                             | DNS Zone Xfer
ip xfrm state list                                     | Print existing VPN keys
ip addr add <ip>/<cird> dev eth0                       | Adds `hidden' interface
/var/log/messages | grep DHCP                          | List DHCP assignments
tcpkill host <ip> and port <port>                      | Block ip:port
echo "1" > /proc/sys/net/ipv4/ip_forward               | Turn on IP Forwarding
echo "nameserver x.x.x.x" > /etc/resolv.conf           | Add DNS Server

## Linux System Info
Command                                                | Description
------------------------------------------------------ | ----------------------------------
nbtstat -A <ip>                                        | Get hostname for <ip>
id                                                     | Current username
w                                                      | Logged on user
who -a                                                 | User information
last -a                                                | Last users logged on
ps -ef                                                 | Process listing (top)
df -h                                                  | Disk usage (free)
uname -a                                               | Kernel version/CPU info
mount                                                  | Mounted file systems
getent passwd                                          | Show list of users
PATH=$PATH:/home/mypath                                | Add to PATH variable
kill <pid>                                             | kills process with <pid>
cat /etc/issue                                         | Show OS info
cat /etc/*release*                                     | Show OS version info
cat /proc/version                                      | Show kernel info
rpm --query -all                                       | Installed pkgs (Redhat)
rpm -ivh *.rpm                                         | Install RPM (-e=remove)
dpkg -get-selections                                   | Installed pkgs (Ubuntu)
dpkg -I *.deb                                          | Install DEB (-r=remove)
pkginfo                                                | Installed pkgs (Solaris)
which <tscsh/csh/ksh/bash>                             | Show location of executable
chmod 750 <tcsh/csh/ksh>                               | Disable <shell>, force bash

## Linux Utility Commands
Command                                                | Description
------------------------------------------------------ | ----------------------------------
wget http://<url> -O url.txt -o /dev/null              | Grab url
rdesktop <ip>                                          | Remote Desktop to <ip>
scp /tmp/file user@x.x.x.x:/tmp/file                   | Put file
scp user@<remoteip>:/tmp/file /tmp/file                | Get file
useradd -m <user>                                      | Add user
passwd <user>                                          | Change user password
rmuser uname                                           | Remover user
script -a <outfile>                                    | Record shell : Ctrl-D stops
apropos <subject>                                      | Find related command
history                                                | View users command history
!<num>                                                 | Executes line # in history

## Linux File Commands
Command                                                | Description
------------------------------------------------------ | ----------------------------------
diff file1 file2                                       | Compare files
rm -rf <dir>                                           | Force delete of <dir>
shred -f -u <file>                                     | Overwrite/delete file
touch -r <ref_file> <file>                             | Matches ref_file timestamp
touch -t YYYYMMDDHHSS <file>                           | Set file timestamp
sudo fdisk -l                                          | List connected drives
mount /dev/sda# /mnt/usbkey                            | Mount USB key
md5sum -t file                                         | Compute md5 hash
echo -n "str" | md5sum                                 | Generate md5 hash
sha1sum file                                           | SHA1 hash of file
sort -u                                                | Sort/show unique lines
grep -c "str" file                                     | Count lines w/ "str"
tar cf file.tar files                                  | Create .tar from files
tar xf file.tar                                        | Extract .tar
tar czf file.tar.gz files                              | Create .tar.gz
tar xzf file.tar.gz                                    | Extract .tar.gz
tar cjf file.tar.bz2 files                             | Create .tar.bz2
tar xjf file.tar.bz2                                   | Extract .tar.bz2
gzip file                                              | Compress/rename file
gzip -d file.gz                                        | Decompress file.gz
upx -9 -o out.exe orig.exe                             | UPX packs orig.exe
zip -r <zipname.zip> \Directory\*                      | Create zip
dd skip=1000 count=2000 bs=8 if=file of=file           | Cut block 1K-3K from file
split -b 9K \<fiile> <prefix>                          | Split file into 9K chunks
awk 'sub("$"."\r")' unix.txt > win.txt                 | Win xompatible txt file
find -i -name <file> -type *.pdf                       | Find PDF files
find / -perm -4000 -o -perm -2000 -exec ls -ldb { } \; | Search for setuid files
dos2unix <file>                                        | Convert to *nix format
file <file>                                            | Determine file type/info
chattr (+/-)i <file>                                   | Set/Unset immutable bit

## Linux Misc Commands
Command                                                | Description
------------------------------------------------------ | ----------------------------------
unset HISTFILE                                         | Disable history logging