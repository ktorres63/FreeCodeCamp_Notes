Cisco IOS is the operating system of cissco network devices such as routers and switches. It provides feaures and services required to manage and operate network devices. This operating system comes in different versions and releases that vary in features suuport and performance.
It offers several features required for the operation of modern networks, such as, but not limited to:

+ Support for IPv6
+ Quality of Service (QoS)
+ Security features such as encryption and authentication
+ Virtualization features such as Virtual Private LAN Service (VPLS)
+ Virtual Routing and Forwarding (VRF)
it supports various network protocols and services required for network operations. These include:
|Protocol Type|Description|
|-|-|
|Routing Protocols|Such as OSPF and BGP are used to route data packets on a network|
|Switching protocols|Such as VLAN Trunking protocol (VTP) and spanning tree protocol (STP) is used to configure and manage switches on a network|
|Network services|Such as Dynamic Host configuration protocol (DHCP) are used to automatically provide clients on the network with IP addresses and other network configurations|
|Security features|Such as Access control List (ACLs) which are used to control access to network resources and prevent security threats|

In cisco IOS, different types od passwords are used for various purposes, for example
|Password Type| Description|
|-|-|
|User|The user password is used for logging in to cisco IOS, it's used to restrict acces to the network device and its features|
|Enable Password| The enable password is used to enter "enable" mode. The "enable " mode is the mode where you have access to advanced functions and settings|
|Secret| The secret is a password to secure access to certain function and services. It's pften used to restrict access to remote management tools and services.
|Enable Secret|The enable secret is an exxtra-secure password used to secure acces to "enable" mode, and they are stores encrypted to porvide additional protection|

The Cisco IOS devices can be configured for SSH or Telnet. So it can be accessed remotely. We can determine from the response we receive that itt is indeed a cisco IOS, as it responds with the User Access Verification message

![[cisco.png]]

## VLANS 
A virtual Local Area Network (VLAN) is a virtual LAN conection that groups devices on a network. VLANs are commonly used to segment network traffic and enhance security features. We can configure and manage VLANs in Cisco IOS and add VLAN tags (VLAN IDs) to data packets to classify them into VLANs.The VLAN tag is a field in the Ethernet frame used to indicate which VLAN a data packet belongs to. Cisco IOS distinguishes between VLAN-tagged and non-VLAN-tagged network traffic.

#### VLAN-Tagged
VLAN-tagged network traffic contains VLAN tags and is used to route and segment data packets between switches.

#### Non-VLAN-Tagged
Non-VLAN-tagged network traffic, on the other hand, is network traffic that does not contain a VLAN tag and is used to route and segment data packets within a switch. All non-VLAN-tagged network traffic is placed in VLAN1.

## Cisco Discovery Protocol
Cisco Discovery Protocol (CDP) is a layer-2 networks protocol from cisco that is used by cisco devices such as routers, switches, and bridges to gather information about other directly connected to cisco devices. This information can be used to discover and track network's topology and help manage and troubleshoots the network This protocol is usually enabled in Cisco devices, but it can be disabled if it is not needed or if it should be disabled for security reasons
![[cdp.png]]

The shown message contains information about the device itself, such as the device name, IP address, port name, and functionality of the router, as well as information about the operating system and hardware platform of the device. Besides, we can see in the first line from the CDPv2 that we are dealing with the Cisco Discovery Protocol.

For comparison we can look at another protocol called Spanning Tree protocol (STP). The STP is a network protocol that ensures no loops in  a network with multiple connections between switches. There are no loops and it prevents data packets from circulating in a loop and congesting the network
![[STP.png]]
In this example, we see that an STP message was sent containing information about the root switch, the MAC address of the root switch, the ID of the port over which the message was sent, and other configuration parameters such as the maximum aging time, hello time, and forward delay.
