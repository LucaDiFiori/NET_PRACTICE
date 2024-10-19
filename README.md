# Table of Contents
- [NET_PRACTICE](#net_practice)
- [COMPUTER NETWORK](#computer-network)
	- [Key components of a computer network](#key-componets-of-a-computer-network)
- [BASIC CHARACTERISTICS](#basic-characteristics)
- [NETWORK PROTOCOLS & COMUNICATIONS](@network-protocols-&-cominications)
	- [What is Data Comunication?](#What-is-Data-Comunication?)
	- [Understand data flow](#Undersand-data-flow)
	- [Protocols in computer network](#protocols-in-computer-network)
		- [Elements of protocol](#know-the-elements-of-protocol)
- [](#)


***
# Sources
- https://youtube.com/playlist?list=PLBlnK6fEyqRgneraVKkEXrwyLVx2vJUvt&si=PTG-t3fgIMkWcgTl
- https://www.youtube.com/watch?v=bj-Yfakjllc&list=PLIFyRwBY_4bRLmKfP1KnZA6rZbRHtxmXi&ab_channel=PracticalNetworking

- https://youtube.com/playlist?list=PLIFyRwBY_4bRLmKfP1KnZA6rZbRHtxmXi&si=v7P3lmUDC_sHd_zd

- https://42-cursus.gitbook.io/guide/rank-04/netpractice/theory

***

# NET_PRACTICE
This project is a general practical exercise to let you discover networking.
You will have to configure small-scale networks. To do so, it will be necessary to understand how TCP/IP addressing works.

# DEFINITION: COMPUTER NETWORK
A computer network is a system of interconnected **nodes** (devices such as computers, servers, and other networking equipment) that **communicate** with each other to share resources and information. These networks can be wired or wireless and operate using protocols that govern data transmission, security, and access.

## Key components of a computer network:
- **Nodes**: Devices like computers, phones, or servers capable of sending/receving data generated by other nodes in the network. We have:
	- **end node (also known as a host)**: any device at the edge of a network that either initiates or receives communication. These devices are typically the sources or destinations of the data being transmitted
	- **intermediate node**: a device within the network that helps route data between end nodes. These nodes don't originate or consume the data but instead forward it from one place to another to ensure it reaches its destination

- **Communication links**: The physical or wireless connections (e.g., cables, radio waves) that allow data to be transmitted between nodes.
- **Switches and routers**: Devices that manage data traffic and direct it between different parts of the network.
- **Protocols**: Standardized rules (like TCP/IP) that dictate how data is transmitted and received.

# BASIC CHARACTERISTICS
Here’s a breakdown of the basic characteristics of a computer network

- **Fault Tolerance**: Fault tolerance is the ability of a network to continue 
  operating smoothly, even when one or more components fail.
  - Networks achieve this by having redundant systems, meaning there are backups 
    or alternative pathways for data to flow if one part of the network fails.

- **Scalability**: Scalability refers to the network's ability to grow and manage 
  increased demand without sacrificing performance.
  (An example of scalable network is Internet)

- **Quality of Service (QoS)**: QoS is the ability to prioritize certain types 
  of network traffic to ensure performance for critical applications.
  - In a network, different types of data (like voice, video, and regular file transfers) 
    compete for bandwidth. QoS ensures that time-sensitive data (e.g., voice or video calls) 
	gets priority over less critical traffic (e.g., file downloads).
	This can be achieved by traffic shaping, bandwidth reservation, and traffic prioritization.

- **Security**: Security refers to the measures taken to protect the network 
  from unauthorized access, attacks, and data breaches.


# NETWORK PROTOCOLS & COMUNICATIONS
## What is Data Comunication?
Data communication is the exchange of data between nodes (such as computers, servers, smartphones, etc.) 
over a transmission medium (or link).

## Understand data flow
Data flow describes the direction in which data is transmitted between devices. T
here are three types:
- **Simplex**: Data flows in only one direction. For example, in a keyboard-to-computer 
  connection, the keyboard sends data to the computer, but the computer doesn’t send data back.
- **Half-Duplex**: Data can flow in both directions, but only one direction at a time. 
  Walkie-talkies are a good example of this.
- **Full-Duplex**: Data flows in both directions at the same time. A common example 
  is a telephone conversation where both people can speak and listen simultaneously.

## Protocols in computer network
- **Definition**: Protocols are a set of rules that govern how data is transmitted and received over a network. 
  These rules ensure that devices can communicate with each other reliably and consistently.
- **Why they are important**:
	- **Interoperability**: Protocols ensure that devices from different manufacturers or platforms can communicate. For example, TCP/IP is the protocol used for communication over the internet, allowing millions of different devices to connect.
	- **Error Handling**: Protocols provide methods for detecting and correcting errors during transmission, ensuring that data is received accurately.
	- **Flow Control**: They regulate how fast data can be sent and received, preventing a fast sender from overwhelming a slower receiver.
	- **Security**: Many protocols include encryption and authentication mechanisms to secure data as it moves across a network.
- **Example protocols**:
	- **HTTP**: Used for transmitting web pages.
	- **TCP/IP**: The fundamental protocol suite for internet communication.
	- **FTP**: Used for transferring files between a client and server.
	- **SMTP**: Used for sending emails.

### Elements of protocol
Protocols used in network communications define:
- **Message Encoding**: Message encoding is the process of converting data into a format that can be transmitted over a network.
  (Protocols like ASCII or Unicode are used for encoding text, while audio and video have their own encoding standards (e.g., MP3, MPEG).)
- **Message Formatting & Encapsulation**:
	- **Message Formatting**: Refers to the specific structure that a message must follow 
	  to be properly understood by the receiving system. It involves organizing the 
	  data into sections such as headers, footers, and payloads.
	  For instance, an email protocol like SMTP has a header (sender, receiver, subject) and a body (message content).
	- **Encapsulation**: This refers to wrapping data with protocol-specific information as 
	  it moves through different layers of the network (according to the OSI model).
	  For example, when sending data over the internet, a message is encapsulated 
	  with IP headers, then TCP/UDP headers, and finally, the application-specific headers (like HTTP).
	  At each step, new information is added to help the message reach its destination and be understood properly.
- **Message Timing**: Message timing refers to when and how fast data is sent between devices.
	- **Flow Control**: Ensures that data is sent at a rate that the receiver can handle, preventing data loss or overload.
	- **Response Time**: iming protocols define how quickly a receiver must acknowledge receipt of a message, preventing unnecessary delays.
	- **Synchronization**: iming protocols define how quickly a receiver must acknowledge receipt of a message, preventing unnecessary delays.
- **Message Size**: Message size refers to how large a data packet can be when sent across the network.
  Different networks have limits on how much data can be transmitted at once. For example, 
  Ethernet networks often use a maximum transmission unit (MTU) size of around 1500 bytes.
- **Message Delivery Options**: This refers to how data is delivered to the recipient. There are three primary options:
	- **Unicast**: Data is sent from one sender to one specific receiver. This is the most common form of communication, such as sending an email or visiting a website.
	- **Multicast**: Data is sent from one sender to multiple specific receivers. An example is streaming media to multiple users in a private group.
	- **Broadcast**: Data is sent from one sender to all devices on a network. This is often used in local networks to send data like ARP (Address Resolution Protocol) requests.
