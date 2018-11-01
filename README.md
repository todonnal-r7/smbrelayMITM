# smbrelayxMITM

This is a modified copy of the original smbrelayx.py packaged with the Impacket tools.

There is only one modification that has been made. This version listens on port 4445 rather than 445.

By listening on a non-standard port, we can perform a man-in-the-middle attackusing tools such as ettercap, bettercap, MITM Framework, etc. and use iptables to redirect all port 445 packets to port 4445 and have smbrelayxMITM relay the hash to the target of your choice.

Example IPTables rule: iptables -t nat -A PREROUTING -i eth0 -p tcp --dport 445 -j REDIRECT --to-port 4445

smbrelayxMITM.py requires the Impacket tools to work: https://github.com/SecureAuthCorp/impacket.git

*** This file has dependencies in the original Impacket package. Place smbrelayxMITM.py in the impacket/examples folder of the original package and run it from there. ***
