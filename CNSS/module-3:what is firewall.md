# 3.1 What is a Firewall 

A firewall is a fence between your computer or your internal network and the outside world or the Internet. A particular firewall implementation might use one or more of the methods listed here to provide that barrier.

Packet filtering
Stateful packet filtering
User authentication
Client application authentication
At a minimum, a firewall will filter incoming packets based on parameters such as packet size, source IP address, protocol, and destination port.

As you may already know, both Linux and Windows (this includes every Windows version since XP through the Windows 10 and the server editions) ship with a simple firewall built into the operating system. Norton and McAfee both offer personal firewall solutions for individual PCs. These firewalls are meant for individual machines. 

There are more advanced solutions available for networks. In an organisational setting, you will want a dedicated firewall between your network and the outside world. This might be a router that also has built-in firewall capabilities. (Cisco Systems is one company that is well-known for high quality routers and firewalls.) Alternatively, it might be a server that is dedicated to run firewall software. There are a number of firewall solutions that you can examine. Selecting a firewall is an important decision.

## 3.2 Firewall Types

Packet filtering firewalls are the simplest and often the least expensive type of firewalls. Several other types of firewalls offer their own distinct advantages and disadvantages. The basic types of firewalls are:

- Packet filtering
- Application gateway
- Circuit level gateway
- Stateful packet inspection

### 3.2.1 Packet Filtering Firewall

The packet filtering firewall is the most basic type of firewall. In a packet filtering firewall, each incoming packet is examined. Only those packets that match the criteria you set are allowed through. Many operating systems, such as Windows clients (such as Windows 8 and 10) and many Linux distributions, include basic packet filtering software with the operating system. 

Packet filtering firewalls are also referred to as screening firewalls. They can filter packets based on packet size, protocol used, source IP address, and many other parameters. Some routers offer this type of firewall protection in addition to their normal routing functions.

Packet filtering firewalls work by examining a packet’s source address, destination address, source port, destination port, and protocol type. Based on these factors and the rules that the firewall has been configured to use, they either allow or deny passage to the packet. These firewalls are very easy to configure and inexpensive. Some operating systems, such as Windows 10 and Linux, include built-in packet filtering capabilities.


### 3.2.2 Stateful Packet Inspection

The stateful packet inspection (SPI) firewall is an improvement on basic packet filtering. This type of firewall will examine each packet, denying or permitting access based not only on the examination of the current packet, but also on data derived from previous packets in the conversation. 

This means that the firewall is aware of the context in which a specific packet was sent. This makes these firewalls far less susceptible to ping floods and SYN floods, as well as being less susceptible to spoofing. SPI firewalls are less susceptible to these attacks for the following reasons:

- They can tell whether the packet is part of an abnormally large stream of packets from a particular IP address, thus indicating a possible DoS attack in progress.
- They can tell whether the packet has a source IP address that appears to come from inside the firewall, thus indicating IP spoofing is in progress.
- They can also look at the actual contents of the packet, allowing for some very advanced filtering capabilities.

### 3.2.3 Application Gateway

An application gateway (also known as application proxy or application-level proxy) is a program that runs on a firewall. This type of firewall derives its name from the fact that it works by negotiating with various types of applications to allow their traffic to pass the firewall. In networking terminology, negotiation is a term used to refer to the process of authentication and verification. In other words, rather than looking at the protocol and port the packet is using, an application gateway will examine the client application and the server-side application to which it is trying to connect. 

It will then determine if that particular client application’s traffic is permitted through the firewall. This is significantly different from a packet filtering firewall, which examines the packets and has no knowledge of what sort of application sent them. Application gateways enable the administrator to allow access only to certain specified types of applications, such as web browsers or FTP clients.

When a client program, such as a web browser, establishes a connection to a destination service, such as a web server, it connects to an application gateway, or proxy. The client then negotiates with the proxy server in order to gain access to the destination service. 

In effect, the proxy establishes the connection with the destination behind the firewall and acts on behalf of the client, hiding and protecting individual computers on the network behind the firewall. This process actually creates two connections. There is one connection between the client and the proxy server and another connection between the proxy server and the destination.


### 3.2.4 Circuit Level Gateway

Circuit level gateway firewalls are similar to application gateways but are more secure and generally implemented on high-end equipment. These types of firewalls also employ user authentication, but they do so earlier in the process. 

With an application gateway, first the client application is checked to see if access should be granted, and then the user is authenticated. With circuit level gateways, authenticating the user is the first step. The user’s logon ID and password are checked, and the user is granted access before the connection to the router is established. This means that each individual, either by username or IP address, must be verified before any further communication can take place.

Once this verification takes place and the connection between the source and destination is established, the firewall simply passes bytes between the systems. A virtual “circuit” exists between the internal client and the proxy server. Internet requests go through this circuit to the proxy server, and the proxy server delivers those requests to the Internet after changing the IP address. External users only see the IP address of the proxy server. 

## 3.3 Firewall Implementation

Administrators must be able to evaluate implementation issues to achieve a successful security solution for their systems. Understanding the type of firewall means knowing how the firewall will evaluate traffic and decide what to allow and what not to allow. Understanding the firewall’s implementation means understanding how that firewall is set up in relation to the network it is protecting. The most widely used configurations include:

- Network host-based
- Dual-homed host
- Router-based firewall
- Screened host

### 3.3.1 Host Based

In the host-based (sometimes-called network host-based) scenario the firewall is a software solution installed on an existing machine with an existing operating system. The most significant concern in this scenario is that, no matter how good the firewall solution is, it is contingent upon the underlying operating system. In such a scenario, it is critical that the machine hosting the firewall have a hardened operating system. Hardening the operating system refers to taking several security precautions including:

- Ensuring all patches are updated
- Uninstalling unneeded applications or utilities
- Closing unused ports
- Turning off all unused services

### 3.3.2 Dual-Homed Hosts

A dual-homed host is a firewall running on a server with at least two network interfaces. This is an older methodology. Most firewalls today are implemented in actual routers, rather than servers. The server acts as a router between the network and the interfaces to which it is attached. 

To make this work, the automatic routing function is disabled, meaning that an IP packet from the Internet is not routed directly to the network. The administrator can choose what packets to route and how to route them. Systems inside and outside the firewall can communicate with the dual-homed host, but cannot communicate directly with each other.


### 3.3.3 Router-Based Firewall

Administrators can implement firewall protection on a router. In fact, even the simplest, low-end routers today have some type of firewall included. In larger networks with multiple layers of protection, this is often the first layer of protection. Although various types of firewalls can be implemented on a router, the most common type uses packet filtering. Users of a broadband connection in a home or small office can get a packet filtering firewall router to replace the basic router provided by the broadband company.

In many cases, this solution is also ideal for the firewall novice. A number of vendors supply router-based firewalls that can be preconfigured by the vendor based on the customer’s needs. The customer can then install it between the network and external Internet connection. In addition, most of the widely known brands (Cisco, 3Com, etc.) offer vendor-specific training and certifications in their hardware, making it relatively easy to find qualified administrators or to train current staff.

### 3.3.4 Screened Hosts

A screened host is really a combination of firewalls. In this configuration, a combination of a bastion host and a screening router is used. The combination creates a dual firewall solution that is effective at filtering traffic. The two firewalls can be different types. The bastion host might be an application gateway and the router packet screener (or vice versa). This approach gives the advantages of both types of firewalls and is similar in concept to the dual-homed host.

The screened host has some distinct advantages over the dual-homed firewall. Unlike the dual-homed firewall, the screened host needs only one network interface and does not require a separate subnet between the application gateway and the router. This makes the firewall more flexible but perhaps less secure because its reliance on only one network interface card means that it might be configured to pass certain trusted services to the application gateway portion of the firewall and directly to servers within the network.

## 3.4 Proxy Servers

A proxy server is often used with a firewall to hide the internal network’s IP address and present a single IP address (its own) to the outside world. A proxy server is a server that sits between a client application, such as a web browser, and a real server. Proxy servers prevent hackers from seeing the IP addresses of internal machines, knowing how many machines are behind the proxy server, or learning anything about the network configuration.

Proxy servers also provide a valuable control mechanism because most proxy servers log all outgoing traffic. This enables network administrators to see where employees go on the Internet. A proxy server normally runs as software on the same machine as your firewall.

### 3.4.1 NAT (Network Address Translation)

For many organisations, proxy servers have been superseded by a newer technology known as network address translation (NAT). Today what we call proxy servers don’t do what proxy servers originally did (i.e., translate a private IP address into a public IP address). Primarily, NAT translates internal addresses and external addresses to allow communication between network computers and outside computers. The outside sees only the address of the machine running NAT (often the firewall). From this perspective, it is functioning exactly like a proxy server.

## 3.5 Windows Firewalls

Windows first started shipping a primitive firewall, called Internet Connection Firewall (ICF), with Windows 2000. It was very simple. Each version of Windows since then has expanded upon this idea. Windows 10 ships with a fully functioning firewall. This firewall can block inbound and outbound packets. To access the Windows 10 firewall, click the Start button and type Firewall.

Beginning with Windows Server 2008 and all versions after that, Windows Firewalls are stateful packet inspection firewalls. With the Windows 10 Firewall, you can set different rules for outbound and inbound traffic. For example, your standard workstation will probably allow outbound HTTP traffic on port 80, but you might not want to allow inbound traffic (unless you are running a web server on that workstation).

More importantly, you can apply rules differently depending on where the traffic comes from. You can set up rules for three areas or profiles:

- Domain: For those computers authenticated on your domain.
- Public: For computers from outside your network. You would treat outside traffic more carefully than traffic coming from another machine in your domain.
- Private: Private refers to traffic from your own computer, thus the term private.

## 3.6 Guided Exercise: Configuring Windows Firewall

## 3.7 Linux Firewalls

Linux has firewall capabilities built into the operating system. This has been a part of the Linux operating system for many years, with occasional improvements in the technology.

### 3.7.1 Iptables

The first widely used Linux firewall was called ipchains. It was essentially a chain of rules for filtering traffic. It was first introduced in version 2.2 of the Linux kernel and superseded the previous ipfwadm (which was not widely used). The more modern iptables replaced ipchains and is the primary firewall for Linux. The iptables service was first introduced in Linux kernel 2.4.

On most Linux systems, iptables is installed as /usr/sbin/iptables. However, if it was not included in your particular Linux installation, you can add it later. 

- Packet filtering: This table is the essential part of the firewall. It is a packet filtering firewall and it contains three standard chains: INPUT, OUTPUT, and Forward. The INPUT chain processes incoming packets, and the OUTPUT chain processes traffic sent out from the machine. If the firewall system is also acting as a router, only the FORWARD chain applies to routed packets.
- Network address translation: This table is used for performing network address translation on outbound traffic that initiates a new connection. This is used only if your machine is serving as a gateway or proxy server.
- Packet alteration: This table is used only for specialized packet alteration. It is often called the mangle table because it alters, or mangles, packets. It contains two standard chains. This table might not even be needed for many standard firewalls.

### 3.7.2 Iptables Configuration

Iptables requires some configuration. You can do it through the GUI (KDE, GNOME, etc.) but the shell commands are common to most distributions. Let’s take a look at some common basic configuration.

To cause iptables to function as a basic packet filtering firewall, you need these commands:

- `iptables -F`
- `iptables -N block`
- `iptables -A block -m state --state ESTABLISHED,RELATED -j ACCEPT`


Obviously, that is the most basic and essential iptables configuration. However, here are some others.

To list the current iptables rules use:

- `iptables –L`
To allow communication on a specific port, SSH port 22 and HTTP port 80 for example use:

- `iptables –A INPUT –p tcp –dport ssh –j ACCEPT`
- `iptables –A INPUT –p tcp –dport 80 –j ACCEPT`

## 3.8 Guided Exercise: Configuring iptables Rules

- ` sudo iptables –A INPUT –p tcp --dport ssh –j ACCEPT `
- `sudo iptables –A INPUT –p tcp --dport 80 –j ACCEPT`
- `sudo iptables-save`
ssss