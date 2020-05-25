# Network Security and Cyber Defance

### 1.1 Network Basics

A network is simply a way for machines/computers to communicate. At the physical level,it consists of all the machines you want to connect and them.Indiviual machines are connected either with a physical connection or wirelessly.To connect multiple machnes togather each machine must connect to a hub or switch and then those hubs / switches must connect together.



 ([picture of network])


### 1.1.1 Basic network Structure

Some connection point must exist between your network and the outside world.A barrier is set up between that network and the Internet,Usually in the the form of a firewall.The real essence of network is communication allowing one machine to communicate with another.

The first step in understanding how to defend a network, is having a detailed understanding of how computers communicate over a network.Network interface cards,swithces,routers,hubs and firewalls are the fundamental physical pices of a network.



([Picture of network with firewall])


### 1.1.2 Data Packets

After you have established a connection with the network,you need to send data. the first part is to identify where you want to send it.All computers have an IP address that is a series of four number between 0 to 255 .example 192.168.0.1

The second part is to format the data for transmission.All data is in binary form.This binary data is put into packets,all less than about 65,000 bytes.the first few bytes are the header.that header tells where the packet is going,where it came from and how many more packets are comming as part of this transmission.there is actually more than one header, Some attacker (IP spoofing ) try to change the header of packets in order to give false information.


A packet can have multiple herader.In fact,most packets will have at least three headers.The IP header has infomation such as IP addresses for the source and destination,as well as what protocol the packet is.The TCP header has information such as IP addresses for the source and destinaton,as well as what protocol the packet is.The TCP header has infomation such as port number.The Ethernet header has information such as the MAC address for the source and destination.if a packet is encrypted with Transport layer Security (TLS),it will also have a TLS header.


### 1.1.3 IP Addresses.

An IP version 4 address is a series of four three-digit numbers separated by periods Each of the three-digit numbers must be between 0 to 255.

One of the roles of a gateway router is to perform what is called network address translation (NAT). Using NAT, a router takes the private IP address on outgoing packets and replaces it with the public IP address of the gateway router so that the packet can be routed through the Internet.

> #####  Subnetting 
Subnetting is simply splitting up a network into smaller portions. For example, if you have a network using the IP address 192.168.1.X (X being whatever the address is for the specific computer), then you have allocated 255 possible IP addresses. What if you want to divide that into two separate subnetworks? Subnetting is how you do tha

More technically, the subnet mask is a 32-bit number that is assigned to each host to divide the 32-bit binary IP address into network and node portions. You also cannot just put in any number you want. The first value of a subnet mask must be 255; the remaining three values can be 255, 254, 252, 248, 240, 224, or 128. Your computer will take your network IP address and the subnet mask and use a binary AND operation to combine them.

It may surprise you to know that you already have a subnet mask even if you have not used subnetting. If you have a Class C IP address, then your network subnet mask is 255.255.255.0. If you have a Class B IP address, then your subnet mask is 255.255.0.0. And finally, if it is Class A, your subnet mask is 255.0.0.0.



Subnetting only allows you to use certain, limited subnets. Another approach is CIDR, or classless interdomain routing. Rather to define a subnet mask, you have the IP address followed by a slash and a number. That number can be any number between 0 and 32, which results in IP addresses like these:

192.168.1.10/24 (basically a Class C IP address)
192.168.1.10/31 (much like a Class C IP address with a subnet mask)



IPv6 utilizes a 128-bit address (instead of 32) and utilizes a hex numbering method in order to avoid long addresses such as 132.64.34.26.64.156.143.57.1.3.7.44.122.111.201.5.

There is no subnetting in IPv6. Instead, it only uses CIDR. The network portion is indicated by a slash followed by the number of bits in the address that are assigned to the network portion, such as

/48
/64

There is a loopback address for IPv6, and it can be written as ::/128.


> ###### differences between IPv4 and IPv6 are described here:

- Link/machine-local.
- IPv6 version of IPv4’s APIPA or Automatic Private IP Addressing. So if the machine is configured for dynamically assigned addresses and cannot communicate with a DHCP server, it assigns itself a generic IP address. DHCP, or Dynamic Host Configuration Protocol, is used to dynamically assign IP addresses within a network.
- IPv6 link/machine-local IP addresses all start with fe80::. So if your computer has this address, that means it could not get to a DHCP server and therefore made up its own generic IP address.
- Site/network-local.
- IPv6 version of IPv4 private address. In other words, these are real IP addresses, but they only work on this local network. They are not routable on the Internet.
- All site/network-local IP addresses begin with FE and have C to F for the third hexadecimal digit: FEC, FED, FEE, or FEF.
- DHCPv6 uses the Managed Address Configuration Flag (M flag).
- When set to 1, the device should use DHCPv6 to obtain a stateful IPv6 address.
- Other stateful configuration flag (O flag).
- When set to 1, the device should use DHCPv6 to obtain other TCP/IP configuration settings. In other words, it should use the DHCP server to set things like the IP address of the gateway and DNS servers


### 1.1.4 Uniform Resource Locator (URL)



### 1.1.5 MAC Addresses

MAC addresses are an interesting topic. A MAC address is a unique address for a network interface card (NIC). Every NIC in the world has a unique address that is represented by a six-byte hexadecimal number. The Address Resolution Protocol (ARP) is used to convert IP addresses to MAC addresses. So, when you type in a web address, the DNS protocol is used to translate that into an IP address. The ARP protocol then translates that IP address into a specific MAC address of an individual NIC.

IEEE assigns the first three bytes (24 bits) of the MAC address to a vendor. This part of the address is known as Organizationally Unique Identifier (OUI). The OUI helps professionals to determine the MAC address manufacturer. The remaining three bytes (24 bits) are assigned by the vendor. The MAC address is equal to 48 bits.


### 1.1.6 Protocols
Different types of communications exist for different purposes. The different types of network communications are called protocols. A protocol is, essentially, an agreed method of communication. In fact, this definition is exactly how the word protocol is used in standard, non-computer usage. Each protocol has a specific purpose and normally operates on a certain port. The table below lists some of the most important protocols.



## 1.2 Guided Exercise: Analysing Network Traffic

Wireshark is already installed and you may start it by openening the Desktop folder called Exercises and then Wireshark. Double click Wireshark to open it. 

([wireshark picture])


## 1.3 Guided Exercise: Analysing Telnet Network Traffic


## 1.4 Basic Network Utilities


### 1.4.1 ipconfig

The first thing you want to do is get information about your own system. To accomplish this, you must get a command prompt. In Windows, you do this by going to the Start menu, selecting All Programs, and then choosing Accessories. You can also go to Start, Run, and type cmd to get a command prompt. In Windows 10 you go to Search and type cmd. Now you can type in ipconfig. (You could input the same command in UNIX or Linux by typing in ifconfig from the shell.) After typing in ipconfig (ifconfig or ip addr in Linux), you should see something much like the below screenshot

([CMD ipconfig picture])

### 1.4.2 ping

Another common used command is ping. Ping is used to send a test packet, or echo packet, to a machine to find out whether the machine is reachable and how long the packet takes to reach the machine. This useful diagnostic tool can be employed in elementary hacking techniques. Figure 1-3 shows the command


([Ping picture])

The above command shows that a 32-byte echo packet was sent to the destination and returned. The TTL means “time to live.” That time unit is how many intermediary steps, or hops, the packet should take to the destination before giving up. Remember that the Internet is a vast conglomerate of interconnected networks. Your packet probably won’t go straight to its destination. It will have to take several hops to get there. As with ipconfig, you can type in ping -? to find out various ways you can refine your ping



### 1.4.3 tracert

The next command is tracert. This command is a sort of “ping deluxe.” Tracert not only tells you whether the packet got there and how long it took, but it also tells you all the intermediate hops it took to get there. (This same command can be executed in Linux or UNIX, but it is called traceroute rather than tracert.) You can see this utility in Figure 1-4.

[(tracert picture)]


### 1.4.4. netstat

Netstat is another interesting command. It is an abbreviation for Network Status. Essentially, this command tells you what connections your computer currently has. Don’t panic if you see several connections; that does not mean a hacker is in your computer. You will see many private IP addresses. This means your network has internal communication going on. You can see this in Figure 1-5.

Certainly, other utilities can be used when working with network communications. However, the four we just examined are the core utilities. These four (ipconfig, ping, tracert, and netstat) are absolutely essential to any network administrator.


([Netstat picture])

### 1.5 Guided Exercise: Using Basic Network Utilities

### 1.6 The OSI Model

The Open Systems Interconnect (OSI) model describes how networks communicate (see Table 1-3). It describes the various protocols and activities and states how the protocols and activities relate to each other. This model is divided into seven layers. It was originally developed by the International Organisation for Standardization (ISO) in the 1980s.


([Picutre of OSI model])

### 1.7 Threat Classification

Your network certainly faces real security threats, and these threats can manifest themselves in a variety forms. There are different ways one might choose to classify the various threats to your system. You could choose to classify them by the damage caused, the level of skill required to execute the attack, or perhaps even by the motivation behind the attack. For our purposes we categorize attacks by what they actually do. Based on that philosophy most attacks can be categorized as one of three broad classes:

Intrusion
Blocking
Malware
Figure 1-6 shows the three categories. The intrusion category includes attacks meant to breach security and gain unauthorised access to a system. This group of attacks includes any attempt to gain unauthorised access to a system. This is generally, what hackers do. The second category of attack, blocking, includes attacks designed to prevent legitimate access to a system. Blocking attacks are often called denial of service attacks (or simply DoS). In these types of attacks, the purpose is not to actually get into your system but simply to block legitimate users from gaining access. The third category of threats is the installation of malware on a system. Malware is a generic term for software that has a malicious purpose. It includes virus attacks, Trojan horses, and spyware. 


#### 1.7.1 Malware

Malware is probably the most common threat to any system, including home users’ systems, small networks, and large enterprise wide-area networks. One reason is that malware is designed to spread on its own, without the creator of the malware having to be directly involved. This makes the malware attack much easier to spread across the Internet, and hence more widespread.
Another type of malware, often closely related to the virus, is the Trojan horse. The term is borrowed from the ancient tale. In this tale, the city of Troy was besieged for a long period of time, but the attackers could not gain entrance. They constructed a huge wooden horse and left it one night in front of the gates to Troy. The next morning, the residents of Troy saw the horse and assumed it a gift, consequently rolling the wooden horse into the city. Unbeknownst to them, several soldiers were hidden inside the horse. That evening, the soldiers left the horse, opened the city gates, and let their fellow attackers into the city.

#### 1.7.2 Intrusions

Intrusions are those attacks that are actually trying to intrude into the system. They are different from attacks that simply deny users access to the system (blocking), or attacks that are not focused on a particular target such as viruses and worms (malware). Intrusion attacks are designed to gain access to a specific targeted system and are commonly referred to as hacking, although that is not the term hackers use. Hackers call this type of attack cracking, which means intruding onto a system without permission, usually with malicious intent. Any attack designed to breach security, either via some operating system flaw or any other means, can be classified as cracking.

#### 1.7.3 Denial of Service

The third category of attacks is blocking attacks, an example of which is the denial of service attack (DoS). In this attack, the attacker does not actually access the system, but rather simply blocks access to the system from legitimate users. In the words of the CERT (Computer Emergency Response Team) Coordination Centre (the first computer security incident response team), “A ‘denial-of-service’ attack is characterised by an explicit attempt by attackers to prevent legitimate users of a service from using that service.” One often-used blocking method is flooding the targeted system with so many false connection requests that it cannot respond to legitimate requests. DoS is an extremely common attack method.

###