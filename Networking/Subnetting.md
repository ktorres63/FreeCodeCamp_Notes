The division of an address range of IPv4 addresses into several smaller address ranges is called subnetting
A subnet is a logical segment of a network tha uses IP addresses with the same network address. We can think of a subnet as a labeled entrance on a large building corridor. With the help of subnetting, we can create a specific subnet by ourselves or find outh the following outline of the respective network
+ Network Address
+ Broadcast Address
+ First host
+ Last host
+ Number of hosts

Let us the following IPv4 address and subnet mask as an example
+ IPv4 Address: 192.168.12.160
+ Subnet Mask: 255.255.255.192
+ CIDR: 192.168.12.160/26

We already know that an IP address is dividided into the network part and the host part

![[networlkpart.png]]

**In subnetting, we use the subnet mask as a template for the IPv4 address. From the 1-bits in the subnet mask, we know which bits in the IPv4 address cannot be changed. These are fixed and therefore determine the main network in which the subnet is located**


![[hostpart.png]]
The bits in the host part can be changed to the first and last address. The first is the network address, and the last address is the broadcast address for the respective subnet
The network address is vital for the delivery of a data packet. If the network addres is the same for the source and destination address, the data packet is delivered within the same subnet. If the network addresses are different, the data packet must be routed to another subnet via the default gateway.
**The subnet mask determines where this separation occurs**
![[separation.png]]
### Network Address
So if we now set all bit to 0 in the host part of the IPv4 address, we get the respective subnet's network address
![[networkA.png]]
### Broadcast Address
If we see all bit in the host part of the IPv4 address to 1, we get the broadcast address 
![[broadcastA.png]]
Since we now know that the IPv4 addresses 192.168.12.128 and 192.168.12.191 are assigned, all other IPv4 addresses are accordingly between 192.168.12.129-190. Now we know that this subnet offers us a total of 64 - 2 (network address & broadcast address) or 62 IPv4 addresses that we can ssign to our host

**2^host's bits -2 = available addresses**
2^6 -2 = 62
|Host|IPv4|
|-|-|
|Network Address|192.168.12.128|
|First Host|192.168.12.129|
|Other Host|...|
|Last Host|192.168.12.190|
|Broadcast Address|192.168.12.191|

## Subnetting into smaller networks
Let us now assume that we, as administrators, have been given the task of dividing the subnet assigned to us into 4 additional subnets. Thus, it's essential to know that we can only divide the subnets based on the binary system
![[subnetingintoSmaller.png]]
Therefore we can divide the 64 hosts we know by 4. The 4 is equal to the exponent 2^2 in the binary system,so we find out the number of bits for the subnet mask by which we have to extend it. So we know the following parameters
+ Subnet: 192.168.12.128/26
+ Required Subnets: 4

Now we increase/expxand our subnet mask by 2 bits from /26 to /28 and it looks like this
![[subneting2.png]]
Next, we can divide the 64 IPv4 addresses that are available to us into 4 parts
|host|Math|Subnets|Host range for each subnet|
|-|-|-|-|
|64|/|4|=16|

So we know how big each subnet will be. From now on, we start from the network address given to us 192.168.12.128 and add 16 host 4 times
![[subneting3.png]]

## Mental Subnetting
It may seem like there is a lot of math involved in subnetting, but each octet repeats itself, and everything is a power of 2 so there doesn't have to be a lot of memorization. The first thing to do is identify what octet changes
|1st octect| 2nd octet|3rd octet|4th octet|
|-|-|-|-|
|/8|/16|/24|/32|
It's possible to identify what octet of the IP address may change by remembering those 4 numbers. Given the network address: 192.168.1.1
/25, it's immediately apparent that 192.168.2.4 would not be in the same network because the /25 subnet means only the fourth octet may change.
The next part identifies how big each subnet can be but by dividing eight by the network and looking and looking at the remainder. This is also called Modulo Operation(%) and is heavily utilized in criptology. Given our previous example of /25, (25 % 8) would be 1. This is because eight goes into 25 three times (8 * 3 = 24). There is a 1 leftover, which is the network bit reserved for the network mask.
There is a total of eight bits in each octet of an IP Address. If one is used for the network mask, the equation becomes 2^(8-1) or 2^7, 128. The table below contains all the numbers.
![[subneting4.png]]
By remembering the powers of two up to eight, it can become an instant calculation. However, if forgotten, it may be quicker to remember to divide 256 in half the number of times of the remainder.
The tricky part of this is getting the actual IP Address range because 0 is a number and not null in networking. So in our /25 with 128 IP Addresses, the first range is 192.168.1.0-127. The first address is the network, and the last is the broadcast address, which means the usable IP Space would become 192.168.1.1-126. If our IP Address fell above 128, then the usable ip space would be 192.168.129-254 (128IPs the network and 255 is the broadcast).