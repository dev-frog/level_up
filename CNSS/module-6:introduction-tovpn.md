## 6.1 Introduction to VPN

Virtual Private Networks (VPNs) are a common way to connect remotely to a network in a secure fashion. A VPN creates a private network connection over the Internet to connect remote sites or users together. Instead of using a dedicated connection, a VPN uses virtual connections routed through the Internet from the remote site or user to the private network. Security is accomplished by encrypting all the transmissions.

A VPN allows a remote user to have network access just as if were local to the private network. This means not only connecting the user to the network as if the user were local but also making the connection secure. Because most organisations have many employees traveling and working from home, remote network access has become an important security concern. Users want access, and administrators want security. The VPN is the current standard for providing both.

## 6.2 VPN Protocols

Multiple ways exist to achieve the encryption needs of a VPN. Certain network protocols are frequently used for VPNs. The two most commonly used protocols for this purpose are Point-to-Point Tunnelling Protocol (PPTP) and Layer 2 Tunnelling Protocol (L2TP). The part of the connection in which the data is encapsulated is referred to as the tunnel. L2TP is often combined with IPSec to achieve a high level of security. 


### 6.2.1 PPTP

PPTP is a tunnelling protocol that enables an older connection protocol, PPP (Point-to-Point Protocol), to have its packets encapsulated within Internet Protocol (IP) packets and forwarded over any IP network, including the Internet itself. PPTP is often used to create VPNs. PPTP is an older protocol than L2TP or IPSec. Some experts consider PPTP to be less secure than L2TP or IPSec, but it consumes fewer resources and is supported by almost every VPN implementation. It is basically a secure extension to PPP.

PPTP was originally proposed as a standard in 1996 by the PPTP Forum—a group of companies that included Ascend Communications, ECI Telematics, Microsoft, 3Com, and U.S. Robotics. This group’s purpose was to design a protocol that would allow remote users to communicate securely over the Internet.

#### 6.2.1.1 Extensible Authentication Protocol (EAP)

EAP was designed specifically with PPTP and is meant to work as part of PPP. EAP works from within PPP’s authentication protocol. It provides a framework for several different authentication methods. EAP is meant to supplant proprietary authentication systems and includes a variety of authentication methods to be used, including passwords, challenge-response tokens, and public key infrastructure certificates.

#### 6.2.1.2 Challenge Handshake Authentication Protocol (CHAP)

CHAP is actually a three-part handshaking (a term used to denote authentication processes) procedure. After the link is established, the server sends a challenge message to the client machine originating the link. The originator responds by sending back a value calculated using a one-way hash function. The server checks the response against its own calculation of the expected hash value. If the values match, the authentication is acknowledged; otherwise, the connection is usually terminated. This means that the authorization of a client connection has three stages.


### 6.2.2 L2TP
Layer 2 Tunnelling Protocol is an extension or enhancement of the Point-to-Point Tunnelling Protocol that is often used to operate virtual private networks over the Internet. Essentially, it is a new and improved version of PPTP. As its name suggests, it operates at the data link layer of the OSI model (like PPTP). Both PPTP and L2TP are considered by many experts to be less secure than IPSec. However, seeing IPSec used together with L2TP to create a secure VPN connection is not uncommon.

Like PPTP, L2TP supports EAP and CHAP. However, it also offers support for other authentication methods, for a total of six:

- EAP
- CHAP
- MS-CHAP
- PAP
- SPAP
- Kerberos


#### 6.2.2.1 MS-CHAP

As the name suggests, MS-CHAP is a Microsoft-specific extension to CHAP. Microsoft created MS-CHAP to authenticate remote Windows workstations. The goal is to provide the functionality available on the LAN to remote users while integrating the encryption and hashing algorithms used on Windows networks.

Wherever possible, MS-CHAP is consistent with standard CHAP. However, some basic differences between MS-CHAP and standard CHAP include the following:

The MS-CHAP response packet is in a format designed for compatibility with Microsoft’s Windows networking products.
The MS-CHAP format does not require the authenticator to store a clear-text or reversibly encrypted password.
MS-CHAP provides authenticator-controlled authentication retry and password-changing mechanisms. These retry and password-changing mechanisms are compatible with the mechanisms used in Windows networks.
MS-CHAP defines a set of reason-for-failure codes that are returned in the failure packet’s message field if the authentication fails. These are codes that Windows software is able to read and interpret, thus providing the user with the reason for the failed authentication.


#### 6.2.2.2 PAP

Password Authentication Protocol (PAP) is the most basic form of authentication. With PAP, a user’s name and password are transmitted over a network and compared to a table of name-password pairs. Typically, the passwords stored in the table are encrypted. However, the transmissions of the passwords are in clear text, unencrypted, the main weakness with PAP. The basic authentication feature built into the HTTP protocol uses PAP. This method is no longer used and is only presented for historical purposes.

#### 6.2.2.3 SPAP

Shiva Password Authentication Protocol (SPAP) is a proprietary version of PAP. Most experts consider SPAP somewhat more secure than PAP because the username and password are both encrypted when they are sent, unlike with PAP. 

Because SPAP encrypts passwords, someone capturing authentication packets will not be able to read the SPAP password. However, SPAP is still susceptible to playback attacks (that is, a person records the exchange and plays the message back to gain fraudulent access). Playback attacks are possible because SPAP always uses the same reversible encryption method to send the passwords over the wire.

#### 6.2.2.4 Kerberos

Kerberos is one of the most well-known network authentication protocols. It was developed at MIT and it’s named from the mythical three-headed dog that guarded the gates to Hades.

Kerberos works by sending messages back and forth between the client and the server. The actual password (or even a hash of the password) is never sent. That makes it impossible for someone to intercept it. What happens instead is that the username is sent. The server then looks up the stored hash of that password, and uses that as an encryption key to encrypt data and send it back to the client. The client then takes the password the user entered, and uses that as a key to decrypt the data. If the user entered the wrong password, then it will never get decrypted. This is a clever way to verify the password without ever being transmitted. Authentication happens with UDP (User Datagram Protocol) on port 88.

## 6.3 IPSec

Internet Protocol Security (IPSec) is a technology used to create virtual private networks. IPSec is used in addition to the IP protocol that adds security and privacy to TCP/IP communication. IPSec is incorporated with Microsoft operating systems as well as many other operating systems. 

For example, the security settings in the Internet Connection Firewall that ships with Windows XP and later versions enables users to turn on IPSec for transmissions. IPSec is a set of protocols developed by the IETF (Internet Engineering Task Force; www.ietf.org) to support secure exchange of packets. IPSec has been deployed widely to implement VPNs.

This is more secure than transport mode but can work more slowly. At the receiving end, an IPSec-compliant device decrypts each packet. For IPSec to work, the sending and receiving devices must share a key, an indication that IPSec is a single-key encryption technology. IPSec also offers two other protocols beyond the two modes already described:

- Authentication Header (AH): The AH protocol provides a mechanism for authentication only. AH provides data integrity, data origin authentication, and an optional replay protection service. Data integrity is ensured by using a message digest that is generated by an algorithm such as HMAC-MD5 or HMAC-SHA. Data origin authentication is ensured by using a shared secret key to create the message digest.
- Encapsulating Security Payload (ESP): The ESP protocol provides data confidentiality (encryption) and authentication (data integrity, data origin authentication, and replay protection). ESP can be used with confidentiality only, authentication only, or both confidentiality and authentication.

## 6.4 SSL/TLS

A new type of firewall uses SSL (Secure Sockets Layer) or TLS (Transport Layer Security) to provide VPN access through a web portal. Essentially, TLS and SSL are the protocols used to secure websites. If you see a website beginning with HTTPS, then traffic to and from that website is encrypted using SSL or TLS. Today, we almost always mean TLS when we say SSL. It is just that many people became comfortable to saying SSL, and the phrase stuck. This should be obvious from the brief history of SSL/TLS presented here:

- Unreleased SSL v1 (Netscape).
- Version 2 released in 1995 but had many flaws.
- Version 3 released in 1996 (RFC 6101).
- Standard TLS 1.0, RFC 2246, released in 1999.
- TLS 1.1 defined in RFC 4346 in April 2006.
- TLS 1.2 defined in RFC 5246 in August 2008. It is based on the earlier TLS 1.1 spec.
- As of July 2017, TLS 1.3 is a draft and details have not been fixed yet.

## 6.5 VPN Solutions

Regardless of which protocols you use for VPN, you must implement your choice in some software/hardware configuration. Many operating systems have built-in VPN server and client connections. These are generally fine for small office or home situations. However, they might not be adequate for larger scale operations in which multiple users connect via VPN. For those situations, a dedicated VPN solution might be necessary.

### 6.5.1 Cisco Solutions

Cisco offers VPN solutions, including a module that can be added to many of their switches and routers to implement VPN services. It also offers client-side hardware that is designed to provide an easy-to-implement yet secure client side for the VPN.

The main advantage of this solution is that it incorporates seamlessly with other Cisco products. Administrators using a Cisco firewall or Cisco router might find this solution to be preferable. However, this solution might not be right for those not using other Cisco products and those who do not have knowledge of Cisco systems. However, many attractive specifications for this product include the following:


### 6.5.2 Openswan

The Openswan product (www.openswan.org/) is an open source VPN solution available for Linux operating systems. As an open source product, one of its biggest advantages is that it is free. Openswan uses IPSec, making it a highly secure VPN solution.

Openswan supports either remote users logging on via VPN, or site-to-site connections. It also supports wireless connections. However, it does not support NAT (network address translation, the new alternative to proxy servers).