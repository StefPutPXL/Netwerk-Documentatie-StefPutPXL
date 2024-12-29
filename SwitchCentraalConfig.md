service password-encryption
!
hostname SwitchCentraal
!
enable secret 5 $1$mERr$NARFGJytzNQ.L1OAZ.TVE/
!
ip domain-name cisco.com
!
username admin privilege 1 password 7 08315442
!
interface Vlan1
 ip address 192.168.0.2 255.255.255.128
!
ip default-gateway 192.168.0.1
!
banner motd ^CUnauthorized access is not allowed!^C
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
