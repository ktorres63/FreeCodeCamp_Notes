Each host in the network located can be identified by the so-called media Access control address(MAC). This would allow data exchange within this one network. If the remote host is located in another network, knowledge of the MAC address is not enough to establish a connection. Addressing on the internet is done via the IPv4 and/or IPv6 address, which is made up of the network address and the host address
It doesn't matter whether it's a smaller network, such as a home computer network, or the entire Internet. The IP address ensures the delivery of data to the correct receiver. We can imagine the representation of MAC and IPv4/IPv6 addresses as follows
+ IPv4/IPv6 - descirbes the unique postal address and district of the reciver¿s building
+ MAC - describes the exact floor and apartment of the receiver

It is possible for a single IP address to address multiple receivers (broadcasting) or for a device to respond to multiple IP addresses. However, it must be ensured that each IP address is assigned only once within the network.
## IPv4 Structure
The most common method od assigning IP addresses is IPv4, which consist of a 32-bit binary number combined into 4 bytes consisting of 8-bit groups(octets) ranging from 0-255. These are converted into more easily readabl decimal numbers, separated by dots and represented as dotted-decimal notation
Thus an IPv4 address can look like this
|Notation|Presentation|
|-|-|
|Binary|0111 1111.0000 0000.0000 0000.0000 0001|
|Decimal|127.0.0.1|

Each network interface(network cards, network printers, or routers) is assigned a unique IP address
The IPv4 format allows 4 294 967 296 unique addresses. The IP address is divided into a host part and a network part. The router assigns the host part of the IP address at home or by an administrator. The respective network administrator assigns the network part. On the internet, this is IANA, which allocates and manages the unique IPs

![[clasesIPv4.png]]
## Subnet Mask
A further separation of these classes into small networks is done with the help of subnetting. This separation is done using the netmasks, which is as long as an IPv4 address. As with classes, it describes which bit positions within the iP address act as network part or host part
![[subnet.png]]
## Network and Gateway Addresses
The 2 additional IPs added in the IPs column are reserved for the so-called network address and the broadcast address. Another important role plays the default gateway, which is the name for the IPv4 address of the router that couples networks and systems with different protocols and manages addresses and transmission methods . It's commoon for the default gatewa to be assigned the first or last assignable IPv4 address in a subnet. This isn't a tecnical requeriment, but has become a de-facto standard in network enviroments of all sizes 
![[network-gatewayAdd.png]]
## Broadcast Address 
The broadcast IP address's task is to connect all devices in a network with each other. Broadcast in a network is a message that is transmitted to all participants of a network and doesn't require any response. In this way, a host sends a data packet to all other participants of the network simultaneously and, in doing so, communicated it IP address, which the receivers can use to contact it. This is the last IPv4 address that is used for the broadcast
![[broadcast.png]]
## Binary system
The binary system is a number system that uses only two different states that are represented into two numbers (0 and 1) opposite to the decimal-system (0 to 9).
An IPv4 address is divided into 4 octets, as we have already seen. Each octet consists of 8 bits. Each position of a bit in an octet has a specific decimal value

## CIDR
Classless Inter-domain Routing (CIDR) is a method of represetation and replaces the fixed assignment between IPv4 address and network classes (A,B,C,D,E). The division is based on the sibnet mask or the so-called CIDR suffix, which allows the bitwise division of the IPv4 address space and thus into subnets of any size. The CIDR suffix indicates how many bits from the beginning of the IPv4 address belong to the network. It's a notation that represents the subnet mask by specifying the number of 1-bits in the subnet mask.
Let us stick to the following IPv4 address and subnet mask as an example 
+ IPv4 Address: 192.168.10.39
+ Subnet Mask: 255.255.255.0
Now the whole representation of the IPv4 address and the subnet mask would look like this
+ CIDR: 192.268.10.39/24

The CIDR suffix is, therefore, the sum of all ones in the subnet mask
![[cidr.png]]