Each host in a network has its own 48-bi(6 octets) Media Access Control(MAC) address, represented in hexadecimal format. MAC is the physical address for our network interfaces. There are several different standards for the MAC address
+ Ethernet (IEEE 802.3)
+ Bluetooth (IEEE 802.15)
+ WLAN (IEEE 802.11)
This is beacause the MAC address addresses the physical connection (Network card, bluetooth or WLAN adapter) of a host. Each network card has its individual MAC address, which is condifgured once on the manufacturer's hardware side but can always be changed, at least temporarily
Example of MAC address:
+ DE:AD:BE:EF:13:37
+ DE-AD-BE-EF-13-37
+ DEAD.BEEF.1337
![[mac_example.png]]
When an IP packet is delivered, it must be addressed on layer 2 to the destination host's physical address or the router /NAT, which is responsible for routing. Each packet has a sender address and destination address
The MAC address consist of a total of 6 bytes. The first half(3 bytes/ 24 bits) is the so-called Organization Unique Identifier (OUI) defined by the insitute of electrical and electronics Engineers (IEEE) for the respective manufacturers
![[mac2.png]]

The last half of the MAC address is called the individual Address Part or Network Interface Controller (NIC) which the manufacturers assign. The manufacturer sets this bit sequence only once and thus ensures that the complete address is unique

![[mac3.png]]

If a host with the IP target address is located in the same subnet, the delivery is made directly to the target computer's physical address. However if this  host belongs to a different subnet, the ethernet frame is addressed to the MAC address of the responsible router (default gateway). If the ethernet frame's destination address matches its own layer 2 address the router will forward the frame to the higher layers. Address resolution protool(ARP) is used in IPv4 to determine the MAC addresses associated with the IP addresses.
As with IPv4 addresses, there are also certain reserved areas for the MAC address. These include, for example the local range for the MAC
![[mac4.png]]
Furthermore, the last 2 bits in the first octet can play another essential role. The last bit can have 2 states 0 and 1, as we already now. The last bit identifies the MAC address as Unicast(0) or Multicast (1). With unicast, it means that the packet sent will reach only one specific host

![[mac5.png]]
With multicast, the packet is sent only once to all host on the local network. Broadcast in a network represents a broadcasted call, where data packets are transmitted simultaneously from one point to all members of a network. It is mainly used if the address of the receiver of the packet is not yet known. An example is the ARP (for MAC addresses) and DHCP (for IPv4 addresses) protocols.

![[mac6.png]]
![[mac7.png]]
The second last bit in the first octet identifies whether it's a global OUI, defined by the IEEE, or a locally administrated MAC address
![[mac8.png]]


## Address Resolution Protocol

Address resolution protocol(ARP) is a network protocol, it's an importnt part of the network communication used to resolve a network layer (layer 3) IP address to a link layer (layer2) MAC address. It maps a host's IP address to it corresponding MAC address to facilitate communication between devices on a Local Area Network (LAN). When a device on a LAN wants to communicate with another device, it sends a broadcast message containing the destination IP address and its own MAC address. The device with the matching IP address responds with its own MAC address, and the 2 devices can then communicate directly using their MAC addresses. This process is known as ARP resolution
ARP is an important part of the network communication process because it allows devices to send and recieve data using MAC addresses rather than ip addresses, which ca be more efficicent. 2 types of request messages can be used
### ARP Request
When a device wants to communicate with another device on a  LAN, it sends an ARP request to resolve the destination device's IP address to its MAC address. The request is broadcast to all devices on the LAN and contains the IP address of the destination device. The device with the matching IP address responds with its MAC address
### ARP Reply
When a device receives an ARP request, it sends an ARP reply to the requesting device with its MAC address. The reply message contains the IP and MAC addresses of both the requesting and the responding devices
![[tshark.png]]

The "who has" message in the first and third lines indicates that a device is requesting the MAC address for the specified IP address, while the second and fourth lines show the ARP reply with the MAC address of the destination device

However it's also vulnerable to attacks such as ARP spoofing which can be used to intercept or manipulate traffic on the network.
However, to protect against such attacks, it is important to implement security measures such as firewalls and intrusion detection systems.
ARP spoofing, also known as ARP cache poisoning or ARP poison routing, is an attack that can be done using tools like Ettercap or cain&abel in which we send falsified ARP messages over a LAN. The goal is to associate our MAC address with the IP address of a legitimate device on the company's network, effectively allowing us to intercept traffic intended for the legitimate device. For example 
![[tshark2.png]]

The first and fourth lines show us(10.129.12.100) sending falsified ARP messages to the target, associating its MAC address with its IP address(10.129.12.101). The second and third lines show the target sending an ARP request and replying to our MAC address. This indicates that we have poisoned the target's ARP cache and that all traffic intended for the target will now be sent to our MAC address
We can use ARP poisoning to perform various activities, such as stealing sensitive information, redirecting traffic, or launching MITM attacks. However, to protect against ARP spoofing, it's important to use secure network protocols, such as IPSec or SSL and to implement security measures, such as firewalls and intrusion detection systems










