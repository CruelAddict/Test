# Test
This one's for testing



*filter
:INPUT ACCEPT [0:0]
:FORWARD ACCEPT [0:0]
:OUTPUT ACCEPT [0:0]
-A INPUT -s 87.236.16.204/32 -p tcp -m tcp --sport 80 -j ACCEPT
-A INPUT -s 8.8.8.8/32 -p udp -m udp --sport 53 -j ACCEPT
-A INPUT -s 77.234.212.55/32 -p tcp -m tcp --sport 20:21 -j ACCEPT
-A INPUT -p tcp -m tcp --sport 110 -j ACCEPT
-A INPUT -s 77.234.212.50/32 -p tcp -m tcp --sport 25 -j ACCEPT
-A INPUT -s 83.0.0.0/16 -p tcp -m tcp --sport 22 -j ACCEPT
-A INPUT -s 10.10.11.173/32 -j DROP
-A INPUT -s 11.0.0.0/8 -p icmp -j DROP
-A INPUT -j DROP
-A FORWARD -d 77.234.213.242/32 -i eth1 -j DROP
-A FORWARD -d 87.236.16.204/32 -o eth1 -p tcp -m tcp --dport 80 -j ACCEPT
-A FORWARD -o eth1 -p tcp -m tcp --dport 80 -j DROP
-A FORWARD -d 8.8.8.8/32 -p udp -m udp --dport 53 -j ACCEPT
-A FORWARD -d 77.234.212.55/32 -p tcp -m tcp --dport 20:21 -j ACCEPT
-A FORWARD -s 8.8.8.8/32 -p udp -m udp --sport 53 -j ACCEPT
-A FORWARD -s 77.234.212.55/32 -p tcp -m tcp --sport 20:21 -j ACCEPT
-A FORWARD -p tcp -m tcp --dport 110 -j ACCEPT
-A FORWARD -p tcp -m tcp --sport 110 -j ACCEPT
-A FORWARD -d 77.234.212.50/32 -p tcp -m tcp --dport 25 -j ACCEPT
-A FORWARD -s 77.234.212.50/32 -p tcp -m tcp --sport 25 -j ACCEPT
-A FORWARD -s 10.10.11.173/32 -j DROP
-A FORWARD -j DROP
-A OUTPUT -d 8.8.8.8/32 -p udp -m udp --dport 53 -j ACCEPT
-A OUTPUT -d 87.236.16.204/32 -o eth1 -p tcp -m tcp --dport 80 -j ACCEPT
-A OUTPUT -o eth1 -p tcp -m tcp --dport 80 -j DROP
-A OUTPUT -d 77.234.212.55/32 -p tcp -m tcp --dport 20:21 -j ACCEPT
-A OUTPUT -p tcp -m tcp --dport 110 -j ACCEPT
-A OUTPUT -d 77.234.212.50/32 -p tcp -m tcp --dport 25 -j ACCEPT
-A OUTPUT -d 83.0.0.0/16 -p tcp -m tcp --dport 22 -j ACCEPT
-A OUTPUT -j DROP
COMMIT
# Completed on Fri Nov 2 10:53:05 2018
# Generated by iptables-save v1.6.0 on Fri Nov 2 10:53:05 2018
*nat
:PREROUTING ACCEPT [1030:76657]
:INPUT ACCEPT [29:10006]
:OUTPUT ACCEPT [928:59547]
:POSTROUTING ACCEPT [574:38013]
-A PREROUTING -i eth1 -p tcp -m tcp --dport 23 -j DNAT --to-destination 11.0.0.2:23
-A POSTROUTING -o eth1 -j MASQUERADE
COMMIT
