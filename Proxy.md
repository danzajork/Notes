__Flush iptables rules__

iptables -F

__Flush iptables rules for the nat table__

iptables -t nat -F

Setup iptables to proxy HTTPS traffic through {server-name}.  Have Burp proxy setup and listening on port 8080.  Ensure Burp's SSL certificate is in the trusted root on the machine.

iptables -t nat -A OUTPUT -p tcp --dport 443 -j DNAT --to-destination {server-name}:8080
