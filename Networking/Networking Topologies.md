
A network topology is a typical arrangement and physical or logical connection of devices in a network. Computers are hosts, such as clients and servers, that actively use the network. They also include network components such as switches, bridges and routers. The network topology determines the components to be used and the access methods to the transmission media
The transmission medium layout used to connect devices is the physical topology of the network. For conductive or glass fiver media, this refers to the cabling plan, the positions of the nodes, and the connections between the nodes and the cabling. In contrast, the logical topology is how the signals act on the network media or how the data will be transmitted across the network from one device to the devices physical connection

We can divide the entire network topology are into three areas.

## 1. Connections
|Wired Connections| Wireless connections|
|---|---|
|Coaxial cabling|Wi-Fi|
|Glass fiber cabling| Cellular|
|Twisted-pair cabling| satellite|

## 2. Nodes - Network interface Controller (NICs)
+ Repeaters
+ Hubs
+ Bridges
+ Switches
+ Router/Modem
+ Gateways
+ Firewalls

Network nodes are the transmission medium's connection points to transmitters and receivers of electrical, optical, or radio signals in the medium. A node may be connected to a computer, but certain types may have only one microcontroller on a node or may have no programmable device at all

## 3. Classifications
We can imagine a topology as a virtual form or structure of a network. This form does not neccesarily correspond to the actual physical arrangement of the devices in the network.
Therefore these topologies can be either physical or logical. For example, the computers on a LAN may be arranged in a circle in a bedroom, but it's very unlikely to have an actual ring topology.
Network topologies are divided into the following eight basic types
+ Point-to-point
+ Bus
+ Star
+ Ring
+ Mesh
+ Tree
+ Hybrid
+ Daisy chain
## Point-to-point 
The simplest network topology with dedicated connection between 2 hosts is the point-to-point topology. In this topology, a direct and straightforward physical link exists only between 2 hosts
Point to point topologies are the basic model of traditional telephony and must not be confused with P2P (peer to peer architecture)
![[point-to-point.png]]
## Bus
All hosts are connected via a transmission medium in the bus topology. Every host has access to the transmission medium and the signals that are transmitted over it. There is no central network comoponent that controls the processes on it. The Transmission medium for this can be for example a coaxial cable
Since the medium is shared with all the other,only one host can send, and all the others can only receive and evaluate the data and see whether it is intended for itself
![[bus.png]]
## Star
The star topology is a network component that maintains a connection to all hosts. Each host is connected to the central network component via a separate link. This is usually a router a hub or a switch. These handle the forwarding function for the data packets. To do this, the data packets are received and forwarded to the destination. The data traffic on the central network component can be very high since all data and connections go through it 
![[star.png]]
## Ring
The physical ring topology is such that each host or node is connected to the ring with 2 cables
+ One for the incoming signals
+ Another for the outgoing ones

This means that one cable arrives ar each host and one cable leaves. The ring topology typically doesn't require an active network component. The control and access to the transmission medium are regulated by a protocol to which all station adhere.

A logical ring topology is based on a phycial star topology, where a distributor at the node simulates the ring by forwarding from one port to the next
The information is transmitted in a predetermined transmission direction. Typically, the transmission medium is acceddes sequentially from station to station using a retrieval system from the central station or a token. A token is a bit pattern that continually passes through a ring network in one direction, which works according to the claim token process
![[ring.png]]

## Mesh
Many nodes decide about the connections on a physical level and the routing on a logical level in meshed networks. Therefore, meshed structures have no fixed topology. There are 2 basic structures from the basic concept: the fully meshed and the partially meshed structure
Each host is connected to every other host in the network in a fully meshed structure. This meansss that rhe hosts are meshed with each other. This technique is primarily used in WAN or MAN to ensure high reliability and bandwith 
In this setup, important network nodes such as routers could be networked together. If one router fails, the others can continue to work without problems, and the network can absorb the failure due to the many connections
Each node of a fully meshed topology has the same routing functions and knows the neighboring nodes it can communicate with proximity to the network gateway and traffic loads
In the partially meshed structure, the endpoints are connected by only one connection. In this type of network topology, specific nodes are connected to exactly one other node, and some other nodes are connected to 2 or more other nodes with a point-to-point connection
![[mesh.png]]

## Tree
The tree topology is an extended star topology that more extensivve local networks havein this structure. This is especially useful when several toppologies are combined. This topology is often used, for wxample, in larger company buildings.
There are both logical tree structures according to the spanning tree and physical ones. mmodular modern networks, based on structured cabling with a hub hierarchy, also have a tree strucure. Tree topologies are also used for broadband networks and city networks (MAN)
![[tree.png]]
## Hybrid
Hybrid networks combine 2 or more topologies so that the resulting network doesn't preset any standard topologies. For example, a tree network can represent a hybrid topology in which star networks are connected via interconnected bus networks. However a tree network that is linked to another tree network is still topologically a tree network. A hybrid topology is always created when 2 different basic network topologies are interconnected
![[hybrid.png]]
## Daisy Chain 
In the daisy chain topology, multiple hosts are connected by placing a cable from one node to another. Since this created a chain of connections, it's also know as a daisy-chain configuration in which multiple hardware components are connected in a series. This type of networking is often found in automation technology (CAN)
Daisy chaining is based on the physical arrangement of the nodes, in contrast to token procedures, which are structural but can be made independent of the physical layouut. The signal is sent to and from a component via its previus nodes to the computer system
![[daisy.png]]
