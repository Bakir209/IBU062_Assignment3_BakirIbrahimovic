devices:
Router 1941
Switch 2960-24TT 2x
PC-PT PC0 IP Address: 168.90.0.2
PC-PT PC1 IP Address: 168.90.0.3
PC-PT PC2 IP Address: 210.3.14.3
Laptop-PT Laptop0 IP Address: 168.90.0.4
Server-PT Server0 IP Address: 210.3.14.2
Server-PT Server1 IP Address: 210.3.14.4

Added 2 new PCs to the switches:
IP addresses: 168.90.0.5 AND 210.3.14.5

EXPLANATIONS OF COMMANDS

enable:
-Switches to privileged EXEC mode

configure terminal
-Enters global configuration mode to allow configuration changes

interface GigabitEthernet0/0
-Accesses the interface named GigabitEthernet0/0 for configuration

ip address 168.90.0.1 255.255.0.0
-Assigns the IP address 168.90.0.1 with subnet mask 255.255.0.0 to the interface

no shutdown
-Activates the interface (interfaces are disabled bz default)

exit
-Exits the current configuration mode

interface GigabitEthernet0/1
-Accesses the interface named GigabitEthernet0/1 for configuration

ip address 210.3.14.1 255.255.255.0
-Assigns the IP address 210.3.14.1 with subnet mask 255.255.255.0 to the interface

no shutdown
-Activates the interface (interfaces are disabled bz default)

exit
-Exits the current configuration mode

ip dhcp pool NET1
-Creates a DHCP pool named NET1

network 168.90.0.0 255.255.0.0
-Defines the IP range (168.90.0.0/16) for the DHCP pool

defult-router 168.90.0.1
-Sets the default gateway (router IP) for DHCP clients as 168.90.0.1

ip dhcp pool NET2
-Creates a DHCP pool named NET2

network 210.3.14.0 255.255.255.0
-Defines the IP range (210.3..14.0/24) for the DHCP pool

default-router 210.3.14.1
-Sets the default gatewayfor DHCP clients as 210.3.14.1


After these commands i had to enable DHCP Gateway to each end device.