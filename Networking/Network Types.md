Each network is structured differently and can be set up individually. For this reason, so-called types and topologies have been developed that can be used to categorize these networks.
### Common Terminology
|Network Type|Definition|
|------------|-------|
|Wide Area Network (WAN)|Internet|
|Local Area Network (LAN) |Internal Networks(Ex. Home or Office)|
|Wireless Local Area Network(WLAN)| Internal Networks accesible over Wifi|

## WAN(Wide Area Network)
The WAN is commonly referred to as the INternet.When dealing with netoworking equipment, we'll often have a WAN address and LAN address. The WAN one is the addres that is generally accessed by the internet. That being said, it's not inclusive to the internet, a WAN is just a large number of LANs  joined together. Many large companies or government agencies will have an "Internal WAN" (also called intranet, Airgap Network, etc). Generall speaking, the primary way we identify if the network is a WAN is to use a WAN specific routing protocol such as BGP and if the IP schema in use is not within RFC 1918(10.0.0.0/8, 172.16.0.0/12, 192.168.0.0/16).

## LAN/WLAN
LANs and WLANs will typically assign IP Addresses designated for local use (RFC 1918, 10.0.0.0/8, 172.16.0.0/12, 192.168.0.0/16). In some cases, like some colleges and hotels, you may be assigned a routable(internet)  IP address from joining their LAN, but is much less common. There's nothing different between a LAN or WLAN, other than WLAN's introduce the ability to transmit data without cables. It is mainly a security designation

## VPN
There are three main types Virtual Private Networks (VPN), but all three have the same goal of making the user feel as if they were plugged into a different network.

### Site to site VPN
Both client and server are network devices, typically either routers or firewalls, and share entire network ranges. This is most commonly ued to join company networks together over the internet, allowing multiple locations to communicate over the internet as if they were local
### Remote Access VPN 
This involves the client's computer creating a virtual interface that behaves as if it is on a client's network. Hack The Box utilizes OpenVPN, which makes a TUN Adapter letting us access the labs. When analyzing these VPNs, an important piece to consider is the routing table that is created when joining the VPN. If the VPN only creates routes for specific networks (ex: 10.10.10.0/24), this is called a Split-Tunnel VPN, meaning the Internet connection is not going out of the VPN. This is great for Hack The Box because it provides access to the Lab without the privacy concern of monitoring your internet connection. However, for a company, split-tunnel VPN's are typically not ideal because if the machine is infected with malware, network-based detection methods will most likely not work as that traffic goes out the Internet.
### SSL VPN
This is essentially a VPN that is done within our web browser and is becoming increasingly common as web browsers are becoming capable of doing anything. Typically these will stream applications or entire desktop sessions to your web browser. A great example of this would be the HackTheBox Pwnbox

## Book Terms
|Network Type| Definition|
|-----|-----|
|Global Area Network (GAN) | Global Network (the internet)|
|Metropolitan Area Network (MAN)|Regional network (multiple LANs)|
|Wireless Personal Area Network (WPAN)| Personal network (Bluetooth)|

## GAN 
A worldwide network such as the Internet is known as a Global Area Network (GAN). However the internet is not only computer network of this kind. Internationally active companies also maintain isolated networks that span several WANs and connect company computers worldwide.
GANs use the glass fibers infraestructure of wide-are networks and interconnect them by international undersea cables or satellite transmission
## MAN
Metropolitan Area Network (MAN) is a broadband telecommunications network that connects several LANs in geographical proximity. As a rule, these are individual branches of a company connected to a MAN via leased lines. High-performance routers and high-performance connections based on glass fibers are used, which enable a significantly higher data throughput than the internet. The transmission speed between two remote nodes is comparable to communications within a LAN

Internationally operating network operators provide the infraestructure for MANs. Cities wired as Metropolitan Area Networks can be integrated supra-regionally in Wide Area Networks(WAN) and internationally in Global Area Networks (GAN)
## PAN / WPAN
Modern end devices such as smarphones, tables, laptops or desktop computers can be connected ad hoc to form a network to enable data exchange. This can be done by cable in the form of a personal Area Network (PAN)
The wireless variant Wireless Personal Area Network (WPAN) is based on Bluetooth or wireless USB technologies. A wireless personal area network that is established via bluetooth is called Piconet. PANs and WANs usually extend only a few meters and are therefore not suitable for connecting devices in separate rooms or even buildings.
In the context of the internet of things (IoT), WPANs are used to communicate control and monitor applications with low data rates. Protocols such as Insteon, Z-wave, and ZigBee were explicity designed for smart homes and home automation

