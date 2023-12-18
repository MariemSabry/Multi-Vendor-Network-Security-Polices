# Multi-Vendor-Network-Security-Polices
 
### Project in Packet Tracer from scratch
Apply All Networks  :
   ip address 172.16.100.0/24
- Point to point    /30
- ip interface   /28
- Routing OSPF 
- Routing OSPF Authentication
- Raduis server on All Router login ---> (method 1 Raduis - method 2 local )
- NTP Server
- SYSLOG Server 
- ---------------------------------------------
Networks for R1: 
  Apply all Switchs
- Vlan 10 HR  172.16.100.16  /28
- Vlan 20 Security 172.16.100.32  /28
- Vlan 99 Management 172.16.100.48  /28
- Vlan 30 off ( ports unused ) 
- Disable DTP
- DHCP Snooping in sw
- (DAI) Dynamic Arp Inspection
- IP & MAC Spoofing 


* Access Ports [
                             -Port fast 
                             -BPDU guard 
                             - STP Mitigation  
                            ]
- ---------------------------------------------
R2  apply : 
 - Loopback (default route and R2 publish inside OSPF )

 - SW(R2) :
       - users ----->  port based security (802.1x ) using raduis server 
       - ntp server on all networks 
       - syslog server on all networks 
       - raduis server [
                                    - 802.1x 
                                    - AAA
                                  ]
- ---------------------------------------------
R4  apply :
 - IPs   [ 
              - Pc9 is considerd inside network 
              - inside  ping to outside but  outside doesn't ping to inside  
              - If there are problems, throw it on the syslog server
            ]
- Create two view 
- First view ( Admin ) --->  all configuration
- Second view (Showview) ---> show commands only

- ---------------------------------------------
R3 apply : 
 - LAN ( wireless devices ) 
 - enable dhcp server ( wireless devices and wired device )
 - WiFi Name NTI 
 - Password cisco12345 
 - Encryption ---> AES
 - Security mode ---> WPA2 Personal 
 - Apply Zone-Base Policy :
                               -  Wireless network is considerd inside network allowed to access outside and DMZ 
                               -  Inside network allowed with all services within the outside
                               -  Outside network allowed only mail and web within DMZ

- ---------------------------------------------
- VPN site to site ( IPsec ) between  R1 and R2  

- ASA apply : 
            - interfaces ( inside, outside , dmz )
            - Nating
            - Policy
            - routing 
- ---------------------------------------------
Basic configuration : 
- hostname 
- privillage password 
- banner 
- lines ( login local ) 
            



