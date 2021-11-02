# Question No. 2
## Create one vm with 2 network interfaces one should behave as WAN and another as LAN.
## Create another vm attaching the previously created LAN interface to it. 
### Implement NAT in the first vm, so that the second vm can access the internet.
   #### Note: Configure the first vm as a router, so make the LAN interfaces in the first vm as gateway to the LAN network. And in the second vm configure the gateway to the ip of the first vm LAN ip
.
## commands used
- > sysctl -w net.ipv4.ip_forward=1
- > echo 1 > /proc/sys/net/ipv4/ip_forward
- > vi /etc/sysctl.d/ip_forward.conf
  - net.ipv4.ip_forward=1
- > sysctl -p /etc/sysctl.d/ip_forward.conf
- > firewall-cmd --permanent --direct --passthrough ipv4 -t nat -I POSTROUTING -o enp0s3 -j MASQUERADE -s enp0s8
- > systemctl restart firewalld.service
- > route add default gw 10.10.1.1
- > systemctl restart network-manager
