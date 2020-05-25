# What you Need to Know

- VirtualBox
- Kali Linux terminal shell
- Windows command shell
- Networking concepts

## Disclaimer

- Testing software sites can be targets for hackers.
- Sites may be flagged as dangerous.
- Tools may be flagged as malware.

### FireWalls

- Most malware comes from the web and email
- Hacking is still an issue
- Firewalls are necessary
  - Personal firewalls
  - Enterprise firewalls


> Firewall Operation
> use picuters


#### Windows firewalls

> `Windows Security > Firewall & protection > `

- Private network.
- Public network.

- Allow an app 
  - Printer connection.
  - add new applications.
- Advanced Security Screen.
- Widnows Defender firewall Propertion

#### Unicast response is allowed to a multicast message.

- unicast responses are sometimes used by hacker to respond to a multicast event.

- Log File 

### Setup Invound and outbound rules.
 

### Windows DNS log Analyser

> Moonpoint.com
> Zedlan 


# Linux Firewalls

### iptables
- `sudo iptables -L -n -v`
- `nc -lp 4545`

#### Setup firewall roules bloack ip

- `sudo ipbables -A INPUT -s 10.0.2.4 -j DROP`
- `sudo iptavles -R INPUT 1 -s 10.0.2.4 -p tcp --dport 4545 -j DROP`

### Remove roules
- `sudo iptables -D INPUT 1`

### Setup remote managment

- `sudo iptables -A INPUT -s 10.0.2.0/24 -p tcp --dport 22 -m connlimit --connlimit-above 2 -j REJECT`
- `sudo iptables -A INPUT -s 10.0.2.0/24 -p tcp --dport 22 -j ACCEPT`


### Limit traffic HTTP and HTTPS

- `sudo iptable -A INPUT -p tcp -m multiport --dport 80,443 -m limit --limit 120.minute --limit-burst 250 -j ACCEPT`

### Drivert Telnet traffic to the honeypot

- `sudo iptables -t nat PREROUTING -p tcp --dport 23 -j DNAT --to 10.0.2.199`
- `sudo iptables -A INPUT -j LOG --log-prefix "tpr-block:"`  Login block ip address
- `sudo iptables -A INPUT -j DROP` block any other input
- Lock configuration `sudo iptables -L -n -v `
- chack nat tables `sudo iptables -t nat -L -n`
- Logfile `cat /var/log/kern.log`


## Firewall Builder

## Port Test/Firewall Tester


## Cisco Firewalls

### Cisco Pix firewall

```bash
PIX> help
PIX>enable
PIX>show configure
PIX>config t
PIX>show username
PIX>username frog password forg
PIX>wri m
PIX>reload
PIX>login 
PIX>ping outside 192.168.0.1
PIX>no ip address outside 23.107.10.2 255.255.255.0
PIX>ip address 192.168.1.254 255.255.255.0
PIX>inferface ethernet0 auto
PIX>ip address inside 10.0.0.1 255.255.255.0
PIX>interface ethernet1 100full
PIX>router outside 0.0.0.0 0.0.0.0 192.168.0.1
PIX>wri m

// access list
PIX>access-group <access-list> in interface <if_name> [per-user-override]
PIX>access-list 1 permit icmp any any
PIX>nat (inside) 101 10.0.0.0 255.255.255.0 0 0
PIX>global (outside) 101 interface
PIX>clear xlate
PIX>wri m
PIX>
PIX>


```

> #### Picture for diagram


### GNS3

- Gain familiarity with the Cisco ASA
- Undersrand enterprise perimeter security
- Approach
  - Tour of GNS3
  - Basic operation
  - Routed Network
  - ASA secure enclave

##### How GNS3 works

- GNS3 configure

```bash

R1#help
R1#show configure
R1#show ip interface brief
R1#config t
R1 (config)#interface fastethernet 0/0
R1 ( config-if)#ip address 10.0.0.1 255.255.255.0
R1 (config-if)#no shutdown
R1 (config-if)#end
R1#config t
R1 (config)#ip route 0.0.0.0 0.0.0.0 10.0.0.2
R1 (config)#exit
R1#write memory
R1#

```

## ASA 



# Web application firewalls

- Protect web  servers and application
- Application layer
- Monitor inbound and outbound traffic
- Block hacker,bots abd spam
- HTTP-oriented asscess control list
- Can break HTTPS

## It can deliver

- Hardware appliances
- Software application
- Cloude services
- Detection
  - Malware signatures
  - Anomalies


> IMPERVA
> amazon 
> Microsft azure
> cloudflare
> Aqronix (opensouce )
> ModSecurity

#### Pipeline code with Jenkins

>wso2 Api Manager


### Honeypots

- Target to lure attackers
  - Identify and prosecute
  - Monitor and analyze
- Types of honeypots
  - Low interaction
  - High interaction
  - Honeynets

> the Honeynet Project

- dockpot
- cowrie


> # cowrie
` `

## Multitier Control Strategy

| Deterrence |
      |
| Prevention |
      |
| Containment |
      |
| Detection and Notification | - | evidence Collection and tracing --- |Assurance|
              |
| Recovery and Restoration   |

### Intrusion Detection System (IDS)

- Signatures updates
  - Business:two to therr hourly
  - Home : daily or weekly
- Alerts are send to a dashboard or SIEM (security information and every management)
- Level 1 security operators filter the alerts
- Level 2 security analysts inverstigate the alerts

### Intrusion Prevention System (IPS)

- An IDS that blocks/blacklist an intrusion
  - Antivirus is an example of IPS
- IPS normally runs in monitoring mode for a while
  - May never progress to active mode
  
### Anomaly Detection System (ADS)

- Monitors to detect malicious behavior
- Builds a model of normal data flows
  - Initially deployed in learning mode
  - When ready,switched to detection mode
- Manual entry for known anomaly thresholds


#### Anomaly Detection Techniqyes

- Protocol content or behavior anomalies
- Statistical anomalies

### Detection Lssues

- False positives - legitimate activity alerted
  - Used as a measure of the quality of the DS
  - Error-prone systems are ignored
- False negatives - intrusion not detected

#### Malicious Websites

- Compromised Web server
- Vulnerable browser

### Blacklist

- List of known malicious websites
- Proxy rejects connections to sites on the list
- Malicious websites may not be on the list

### Whitelist

- list of known good websites
- Proxy only allows connections to sites on the list
- More effective than blacklists

## Snort IDS

- Built on top of tcpdump
- Includes packet analytics and detection rules
- Has plugin capability pre and post-analysis
- Works with the ACID log analyzer
  
### Log and Alert Output

- alert_fast
- alert_full
- Default file /var/logs/snort
- alert_syslog

` apt install snort`

> #### ruls
`cat rulz`
