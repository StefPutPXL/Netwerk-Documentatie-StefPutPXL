service password-encryption
!
hostname RouterISP
!
enable secret 5 $1$mERr$hx5rVt7rPNoS4wqbXKX7m0
!
username admin password 7 08315442
!
ip domain-name pxl.be
!
ipv6 unicast-routing
!
interface GigabitEthernet0/0/0
 ip address 192.168.0.129 255.255.255.128
 ipv6 address FE80::2 link-local
 ipv6 address 2001:DB8:1:1:1:1:81/121
!
ip route 192.168.0.0 255.255.255.128 192.168.0.130 
!
ipv6 route 2001:db8:1:1:1:1:0 /121 2001:db8:1:1:1:1:82
!
banner motd ^CUnauthorized access is forbidden!^C
!
line con 0
 password 7 08315442
 login
!
line vty 0 4
 login local
 transport input ssh
line vty 5 15
 login local
 transport input ssh
!
end
