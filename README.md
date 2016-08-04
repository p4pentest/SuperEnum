# SuperEnum

This script does the basic enumeration of any open port along with screenshots.

Download the below files:
1. superenum
2. commands.config

Process to follow:
1. Place both the files in a folder.
2. Place list of IP Address in a file and give it any name.
3. Open terminal with 'root' user and navigate to the folder where it has been copied in step 1.
4. Run the below command:
./superenum
5. When prompted for input, give the file name as copied in step 2.

Note:
commands.config file has all the commands to execute specific to a port number. This file can be updated easily.

Each command is separated by "@" symbol in the config file. For example currently for port 2049 below is the current entry in the configuration file:
2049@nmap -p$port -Pn --script=nfs-ls $ip | grep "|"@nmap -p$port -Pn --script=nfs-statfs $ip | grep "|"@showmount -e $ip
For adding any other nmap script or command you simply needs to add(highlighted in red) as below:
2049@nmap -p$port -Pn --script=nfs-ls $ip | grep "|"@nmap -p$port -Pn --script=nfs-statfs $ip | grep "|"@showmount -e $ip@nmap -p$port -Pn --script=nfs-showmount $ip | grep "|" 

While adding any command, in place of IP mention as $ip and in place of port number mention as $port
