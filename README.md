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
- /24 becomes /26 (255.255.255.192).
3. Calculate the ranges:
- Subnet 1: 192.168.1.0 - 192.168.1.63
- Subnet 2: 192.168.1.64 - 192.168.1.127
- Subnet 3: 192.168.1.128 - 192.168.1.191
- Subnet 4: 192.168.1.192 - 192.168.1.255


Each subnet has:
- 64 total addresses.
- 62 usable addresses for hosts (excluding network and broadcast addresses).

## Useful Calculations
- Number of subnets: **2^𝑛**, where 𝑛 is the number of bits added to the subnet mask.
- Number of hosts per subnet: **2^𝑚 - 2** , where 𝑚 is the number of bits remaining for hosts.












