A virtual provate Network is a technology that allows a secure and encrypted connection between a provate network and a remote device. This allows the remote machine to access the provate network dirrectly providing secure and confidential access to the network resources and services. Administrators commonly use  VPNs to provide secure and const-effective remote access to a company's network. VPN typically uses the ports TCP/1723 for point-to-point tunneling protocol PPTP  VPN connections and UDP/500 for IKEv1 and IKEv2 VPN connections.
This allows employees to access the network and its resources, such as email and file servers, from remote locations, such as their homes or while traveling. VPNs encrypt the connection between the remote device and the private network, making it much more difficult for attackers to intercept and steal sensitive information. With this, the entire communication is more secure.

Moreover, we can use VPNs to connect multiple remote locations, such as branch offices, into a single private network, making it easier to manage and access network resources. However, several components and requirements are necessary for a VPN to work:

|Requirement|Description|
|-|-|
|VPN Client| This is installed on the remote device and is used to establish and maintain a VPN conncetion with the VPN server. For example this could be an OpenVPN client|
|VPN Server| This is a computer or network device resposible for accepting VPN connections from VPN clients and routing traffic between the VPN clients and the private networks|
|Encryption| VPN connections are encrypted using a variety of encryption algorithms and protocols, such as AES and IPsec, to secure the connection and protect the transmitted data
|Authentication|The VPN server and client must authenticate each pther using a shared secret, certificate, or another authentication method to establish a secure connection|

The VPN client  and server use these ports to establish and maintain the VPN connection. At the TCP/IP layer a VPN connection typically uses the encapsulating Security payload (ESP) protocol to encrypt and authenicate the VPN traffic

## IPsec
Internet Protocol Security (IPsec) is a network security protocol that provides encryption and authentication for internet communications.It is a powerful and widely-used security protocol that provides encryption and authentication for internet communications and works by encrypting the data payload of each IP packet and adding an authentication header (AH), which is used to verify the integrity and authenticity of the packet. IPsec uses a combination of two protocols to provide encryption and authentication:
1. Authentication Header(AH): This protocol provides integrity and authenticity for IP packets but doesn't provide encryption. It adds an authentication header to  each IP packet, which contains a cryptographic cheksum that can be used to verify that packet hasn't been tampererd with
2. Encapsulating Security Payload (ESP): This protocol provides encryption and optional authentication for IP packets. It encrypts the data payload of each IP packet and optionally adds an authentication header, similar to AH.
IPsec can be used in two modes
|Mode|Description|
|-|-|
|Transport Mode| In this mode, IPsec encrypts and authenticates the data payload of each IP packet but doesn't encrypt the IP header. This is tipycally used to secure end-to-end communication between 2 hosts|
|Tunnel Mode|With this mode, IPsecencrypts and authenticates the entire IP packet, including the IP header.This is typically used to create a VPN tunnel between 2 networks|

## PPTP 
Point-to-point Tunneling protocol (PPTP) is also a network protocol that allows the creation of VPNs and works by establishing a secure tunnel between the VPN client and server and then encapsulating the data being transmitted within this tunnel
It's an extension of the PPTP and is implemented in many operating systems. Due to know vulnerabilities PPTP is no longer considered secure today. PPTP can be used to tunnel protocol such as IP, IPX, or NetBEUI via IP. Due to known vulnerabilities, the PPTP is no longer considered secure and has been largely replaced by other VPN protocols such as L2TP/IPsec, IPsec/IKEv2, or OpenVPN. Since 2012, however, PPTP is no longer considered secure because the authentication method MSCHAPv2 uses the dusty DES and can therefore be easily cracked with special hardware.