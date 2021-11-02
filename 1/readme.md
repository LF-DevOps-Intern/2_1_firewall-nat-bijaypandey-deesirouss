# Question No. 1
## Create a virtual machine having the os centos.
- ### Install firewall in the vm(centos might have firewall installed in default).(firewalld or iptables)
- ### Block certain ip range/subnet using firewalld.
- ### Allow http, https and ssh connection using firewall.
- ### You can add other rules as well as you prefer.
	#### Note: The firewall rules should be saved permanently.
## commands used
- > systemctl status firewalld.service
- > firewall-cmd --permanent --add-rich-rule=”rule family=’ipv4’ source address=’192.168.10.0/24’ reject”
- > firewall-cmd --permanent --add-service=http
- > firewall-cmd --permanent --add-service=https
- > firewall-cmd --permanent --add-service=ssh
- > firewall-cmd --permanent --add-service=dhcpd
