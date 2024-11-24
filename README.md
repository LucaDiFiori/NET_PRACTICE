# Sources
## Video
- https://www.youtube.com/playlist?list=PLBlnK6fEyqRgneraVKkEXrwyLVx2vJUvt
- https://www.youtube.com/playlist?list=PLIFyRwBY_4bRLmKfP1KnZA6rZbRHtxmXi
- https://www.youtube.com/playlist?list=PLIFyRwBY_4bQUE4IB5c4VPRyDoLgOdExE
- https://www.youtube.com/watch?v=HQUw0CfQWAM

## Articles
- https://medium.com/@imyzf/netpractice-2d2b39b6cf0a
- https://toufa7.medium.com/netpractice-guidelines-6341b8309f38
- https://toufa7.medium.com/new-subnetting-34fadfb86c70
- https://42-cursus.gitbook.io/guide/rank-04/netpractice/theory
- https://medium.com/@imyzf/netpractice-2d2b39b6cf0a (medium article)

## Repo
- https://github.com/viruskizz/42bangkok-netpractice
- https://github.com/lpaube/NetPractice

***

# NET_PRACTICE
This project is a general practical exercise to let you discover networking.
You will have to configure small-scale networks. To do so, it will be necessary to understand how TCP/IP addressing works.

***

# SUBNETTING
Subnetting is a technique used to divide a larger network into smaller subnetworks (subnets). This improves the efficiency of IP address usage and allows for better network resource management.

## Objectives of Subnetting
1. IP Address Optimization: Reduces the waste of IP addresses.
2. Improved Performance: Limits the size of broadcast domains.
3. Enhanced Security and Organization: Isolates different network segments.


## How Subnetting Works
1. IP Address An IP address consists of two main parts:
	- Network ID: Identifies the network.
	- Host ID: Identifies a device within the network.

For example, in 192.168.1.10/24:
	- 192.168.1 is the Network ID.
	- 10 is the Host ID.
	- /24 indicates that the first 24 bits are reserved for the Network ID (subnet mask: 255.255.255.0).

2. Subnet Mask The subnet mask determines which bits of the address are reserved for the Network ID and which for the Host ID. Common subnet masks include:
	- /24 → 255.255.255.0 (256 addresses, 254 usable hosts)
	- /16 → 255.255.0.0 (65,536 addresses, 65,534 usable hosts)
	- /8 → 255.0.0.0 (16,777,216 addresses, 16,777,214 usable hosts)

3. Network Division Subnetting is done by reducing the number of bits available for hosts and increasing the bits for subnets. For example:
- Starting with 192.168.1.0/24, we can split it into two subnets:
	- 192.168.1.0/25 (128 addresses, 126 usable hosts)
	- 192.168.1.128/25 (128 addresses, 126 usable hosts)


## Practical Example
Let’s assume we have a network with 192.168.1.0/24 and want to divide it into 4 subnets.

1. Determine the number of subnets needed:
	- 4 subnets require at least 2 additional bits to represent them (2² = 4).
2. Adjust the subnet mask:
	- from: 255.255.255.0 = 11111111.11111111.11111111.00000000
	- to: 11111111.11111111.11111111.11000000 -> I took the 2 necessary bits starting from the left (on the network side).
	- /24 becomes /26 (255.255.255.192).
3. Calculate the ranges: 2^m (where 𝑚 is the number of bits remaining for hosts) 
	- Subnet 1: 192.168.1.0 - 192.168.1.63
	- Subnet 2: 192.168.1.64 - 192.168.1.127
	- Subnet 3: 192.168.1.128 - 192.168.1.191
	- Subnet 4: 192.168.1.192 - 192.168.1.255


Each subnet has:
- 64 total addresses.
- 62 usable addresses for hosts (excluding network and broadcast addresses).

## Calculate the range od IP addresses
To calculate the range of IP addresses and determine how many hosts you have per subnet, you need to follow a step-by-step process. Here’s how:

1. **Understand the Subnet Mask**
The subnet mask tells you how many bits are reserved for the network and how many are available for hosts:
- In /26 (255.255.255.192):
	- 26 bits are for the network.
 	- 32−26=6 bits are for the host portion.
 
2. **Calculate the Total Addresses Per Subnet**
The total number of addresses in a subnet is determined by the formula:  **2^n**
Where n is the number of bits in the host portion. For /26, 𝑛 = 6:
2^6 = 64 addresses per subnet.

3. **Calculate the Usable Hosts Per Subnet**
To find the usable host addresses, subtract the network address and the broadcast address from the total:
**2^n -2**

4. **Determine the Range of IP Addresses**
Each subnet has a block size of 2^𝑛 = 64 addresses. The range is calculated as follows:
	- The first IP in the range is the network address (all host bits set to 0).
	- The last IP is the broadcast address (all host bits set to 1).
	- The usable range is from the first usable host to the last usable host.

## Useful Calculations
- **Number of subnets**: **2^𝑛**, where 𝑛 is the number of bits added to the subnet mask.
- **Number of hosts per subnet**: **2^𝑚 - 2** , where 𝑚 is the number of bits remaining for hosts.


***

# SUBNETTING BASE ON REQUIRED HOSTS
Sometimes, instead of determining how many networks you need, you need to calculate the subnets based on the number of hosts you want in each subnet.

## Steps to Subnet Based on Hosts
1. **Determine the Number of Hosts Required**
	- Identify how many devices (hosts) you want to connect in each subnet. For example, let’s say you need 30 hosts.

2. **Calculate the Number of Host Bits Needed**
	- Use the formula: **2^n -2 >= Requires hosts**. n is the number of bits reserved for hosts. The subtraction of 2 accounts for the network address and broadcast address.
	- For 30 hosts: 2^n -2 >= 30 gives me n = 5

3. **Adjust the Subnet Mask**
	- The subnet mask determines how many bits are reserved for the network and how many for hosts.
	- from: 255.255.255.0 = 11111111.11111111.11111111.00000000
	- to: to: 11111111.11111111.11111111.11100000 -> We "save" the 5 necessary bits on the right for the hosts, leaving them as 0 (on the host side), and convert the rest to network bits by setting them to "1".
 	- This gives a subnet mask of /27, equivalent to 255.255.255.224

4. **Calculate the Total Addresses and Usable Hosts Per Subnet**
- Total addresses:
	- 2^n = 32 
- Usable hosts:
	- 2^n - 2 = 30

5. **Determine the Range of IP Addresses**
- Subnet size: 2^n = 32 addresses per subnet.
- Add the subnet size to the starting IP address to calculate the next subnet.
- Example with 192.168.1.0/27:
	- Subnet 1:
		- Network address: 192.168.1.0
		- Usable range: 192.168.1.1 to 192.168.1.30
		- Broadcast address: 192.168.1.31
	- Subnet 2:
		- Network address: 192.168.1.32
		- Usable range: 192.168.1.33 to 192.168.1.62
		- Broadcast address: 192.168.1.63
	- Repeat for additional subnets.










