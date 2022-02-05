# pscan
Multiprocessing Port Scanner

This script performs a ping sweep on an IP or IPs to find active hosts. The active hosts are the port scanned to determine open ports. 

Three simple enumeration features are added as a proof of concept that includes pulling robots.txt if port 80 is open, attempting anonymous login and direcotry listing if port 21 is open, and attempting to send an e-mail thru anonymous SMTP relay if port 25 is open. These features can be modified to perform more in depth enumeration or disabled by commenting out or remiving lines 55 thru 83.

This script was built with mostly default libraries. If using on a pivot host you may need to remove the colorama import and calls if the host does not have the colorama library installed. If requests, ftplib, or smtplib are not installed then remove the basic enumeration in line 55-83.

Targets can be passed as single IP with -t <IP>. A subnet via CIDR notation with -c <CIDR>, passed as a list of IPs in a text file with -f <file name>, or passed as a list of CIDR notation subnets in a file with -cf <file name>.
  
Ports can be passed as a single port with -p <port>, nmap top 10/100/1000 ports with -tp 10, -tp 100, -tp 1000, or all TCP ports with -a.
  
pscan-1.py uses the ping sweep and port scan but removes the colorama and enumeration to be more portable to pviot machines.

Usage:
  python3 pscan.py -t 192.168.1.1 -p 80
  python3 pscan.py -f ips.txt -tp 10
  python3 pscan.py -c 192.168.1.0/24 -tp 100
  python3 pscan.py -cf cips.txt -tp 1000
  
![image](https://user-images.githubusercontent.com/84335647/152627967-464f9865-83f3-4d70-8d87-388332673cef.png)


![image](https://user-images.githubusercontent.com/84335647/152627981-5b5bf197-2d70-4e94-ae06-5f9bdded2e25.png)

 
 ![image](https://user-images.githubusercontent.com/84335647/152627986-6716ca58-d0ca-4b26-841d-d69165fe6882.png)

 ![image](https://user-images.githubusercontent.com/84335647/152628040-3594549c-088d-466f-87bd-e12a9d7c08e9.png)
