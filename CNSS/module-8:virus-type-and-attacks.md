## 8.1 Virus Types and Attacks

Understanding what a virus is, how it spreads, and the different variations is essential for defending against virus threats. You will also need to understand how a virus scanner works in order to make intelligent decisions about purchasing a virus scanner for your organisation.

### 8.1.1 What is a Virus

Most people are familiar with computer viruses, but may not have a clear definition of what is. A computer virus is a program that self-replicates. A virus will also have some other negative functions such as deleting files or changing system settings. However, the self-replication and rapid spread that define a virus. Often this growth, in and of itself, can be a problem for an infected network. It can lead to excessive network traffic and prevent the network from functioning properly. The more a virus floods a network with traffic, the less capacity is left for real work to be performed.


### 8.1.2 What is a Worm

A worm is a special type of virus. Some texts go to great lengths to differentiate worms and viruses, while others treat the worm as simply a subset of a virus. A worm is a virus that can spread without human intervention. In other words, a virus requires some human action in order to infect a machine (downloading a file, opening an attachment, and so on), but a worm can spread without such interaction. In recent years, worm eruptions have become more common than the standard, non-worm virus. Today most of what is called a “virus” is actually a worm.

### 8.1.3 How a Virus Spreads

The best way to combat viruses is to limit their spread, so it is critical that you understand how they spread. A virus will usually spread in one of two ways. The most common, and the simplest, method is to read your e-mail address book and e-mail itself to everyone in your address book. The second method is to simply scan your computer for connections to a network, and then copy itself to other machines on the network to which your computer has access. This is actually the most efficient way for a virus to spread, but it requires more programming skills than the other method.

The first method is, by far, the most common method for virus propagation. Microsoft Outlook may be the one e-mail program most often hit with such virus attacks. The reason is not so much a security flaw in Outlook, as it is the ease of working with Outlook.

Another way a virus can spread is by examining the affected system looking for any connected computers and copying itself to them. This sort of self-propagation does not require user interaction, so the program that uses this method to infect a system is classified as a worm.

#### 8.1.3.1 Rombertik

Rombertik caused chaos in 2015. This malware uses the browser to read user credentials to websites. It is sent as an attachment to an e-mail. Perhaps even worse, in some situations Rombertik will either overwrite the master boot record on the hard drive, making the machine unbootable, or begin encrypting files in the user’s home directory.

#### 8.3.1.2 Shamoon

Shamoon is a computer virus discovered in 2012 designed to target computers running Microsoft Windows in the energy sector. Symantec, Kaspersky Lab, and Seculert announced its discovery on August 16, 2012. It is essentially a data-stealing program that seems to target systems in energy companies. A variant of Shamoon appeared again in 2017. 

Several other viruses, worm and malware exist such as Gameover Zeus, Mirai, Linux Encoder 1, Kedi RAT and much more.


### 8.1.4 Types of Viruses

There are many types of viruses. A virus can be classified by either its propagation method or by its activities on the target computers. 

- Macro: Macro viruses infect the macros in office documents. Many office products, including Microsoft Office, allow users to write mini-programs called macros. These macros can also be written as a virus. A macro virus is written into a macro in some business application. For example, Microsoft Office allows users to write macros to automate some tasks. Microsoft Outlook is designed so that a programmer can write scripts using a subset of the Visual Basic programming language, called Visual Basic for Applications (VBA).
- This scripting language is, in fact, built into all Microsoft Office products. Programmers can also use the closely related VBScript language. Both languages are quite easy to learn. If such a script is attached to an e-mail and the recipient is using Outlook, then the script can execute. That execution can do any number of things, including scanning the address book, looking for addresses, sending out e-mail, deleting e-mail, and more.
- Boot Sector: As the name suggests, a boot sector virus infects the boot sector of the drive, rather than the operating system. This makes them more difficult to eliminate, as most antivirus software works within the operating system.
- Multipartite: Multipartite viruses attack the computer in multiple ways—for example, infecting the boot sector of the hard disk and one or more files.
- Memory resident: A memory-resident virus installs itself and then remains in RAM from the time the computer is booted up to when it is shut down.
- Armored: An Armored virus uses techniques that make it hard to analyse. Code confusion is one such method. The code is written such that if the virus is disassembled, the code won’t be easily followed. Compressed code is another method for armouring the virus.
- Stealth: There are several types of stealth virus. A stealth virus attempts to hide itself from antivirus. A few common methods of stealth are shown below:
 - Sparse infector: A sparse infector virus attempts to escape detection by performing its malicious activities only sporadically. With a sparse infector virus, the user will see symptoms for a short period, then no symptoms for a time. In some cases the sparse infector targets a specific program but the virus only executes every 10th time or 20th time that target program executes. Or a sparse infector may have a burst of activity and then lie dormant for a period of time. There are a number of variations on the theme, but the basic principle is the same: to reduce the frequency of attack and thus reduce the chances for detection.
 - Encrypted: Sometimes a virus is encrypted, even with weak encryption, just enough to prevent an antivirus program from recognizing the virus. Then when it is time to launch an attack, the virus is decrypted.
 - Polymorphic: A polymorphic virus literally changes its form from time to time to avoid detection by antivirus software. A more advanced form of this is called the metamorphic virus; it can completely change itself.


## 8.2 Virus Scanners

The most obvious defence against viruses is the virus scanner. A virus scanner is essentially software that tries to prevent a virus from infecting your system. Usually it scans incoming e-mail and other incoming traffic. Most virus scanners also have the ability to scan portable media devices such as USB drives. 

In general, virus scanners work in two ways. The first method is that they contain a list of all known virus files. Generally, one of the services that vendors of virus scanners provide is a periodic update of this file. This list is typically in a small file, often called a .dat file (short for data). When you update your virus definitions, what actually occurs is that your current file is replaced by the more recent one on the vendor’s website.'


### 8.2.1 Email and Attachment Scanning

Since the primary propagation method for a virus is e-mail, e-mail and attachment scanning is the most important function of any virus scanner. Some virus scanners actually examine your e-mail on the e-mail server before downloading it to your machine. Other virus scanners work by scanning your e-mail and attachments on your computer before passing it to your e-mail program. In either case, the e-mail and its attachments should be scanned prior having any chance to open it and release the virus on your system. This is a critical difference. If the virus is first brought to your machine, and then scanned, there is a chance, however small, that the virus will still be able to infect your machine. Most commercial network virus scanners will scan the e-mail on the server before sending it on to the workstations.

### 8.2.2 Download Scanning
Anytime you download anything from the Internet, either via a web link or with an FTP program, there is a chance you might download an infected file. Download scanning works much like e-mail and attachment scanning, but does so on files you select for downloading.


### 8.2.3 File Scanning
Download and e-mail scanning will only protect your system against viruses that you might get downloading from a site, or that come to you in e-mail. Those methods will not help with viruses that are copied over a network, deposited on a shared drive, or that are already on your machine before you install the virus scanner.

This is the type of scanning in which files on your system are checked to see whether they match any known virus. This sort of scanning is generally done on an on-demand basis instead of an ongoing basis. It is a good idea to schedule your virus scanner to do a complete scan of the system periodically. I personally recommend a weekly scan, preferably at a time when no one is likely to be using the computer.


### 8.2.4 Heuristic Scanning
This is perhaps the most advanced form of virus scanning. This sort of scanning uses rules to determine whether a file or program is behaving like a virus, and is one of the best ways to find a virus that is not a known virus. A new virus will not be on any virus definition list, so you must examine its behaviour to determine whether it is a virus. However, this process is not fool proof. Some actual virus infections will be missed, and some non-virus files might be suspected of being a virus.

### 8.2.5 Active Code Scanning
Modern websites frequently embed active codes, such as Java applets and ActiveX. These technologies can provide some stunning visual effects to any website. However, they can also be vehicles for malicious code. Scanning such objects before they are downloaded to your computer is an essential feature in any quality virus scanner.


### 8.2.6 Instant Messaging Scanning
Instant message scanning is a relatively new feature of virus scanners. Virus scanners using this technique scan instant messaging communications looking for signatures of known virus or Trojan horse files. In recent years the use of instant messaging has increased dramatically. It is now frequently used for both business and recreational purposes. This growing popularity makes virus scanning for instant messaging a vital part of effective virus scanning. If your antivirus scanner does not scan instant messaging, then you should either avoid instant messaging or select a different antivirus package.

## 8.3 Antivirus
There are a number of antivirus packages available for individual computers and for network-wide virus scanning. It is important to consider the following factors when purchasing a virus scanning solution for your own organisation or recommending a solution to a client:

Budget: Price should not be the only, or even the most important, consideration, but it certainly must be considered.
Vulnerability: An organisation with diverse users who frequently get e-mail from outside the organisation or download from the Internet will need more antivirus protection than a small similar group that uses the Internet only occasionally.
Skill: Whoever will ultimately use the product must be able to understand how to use it. Are you getting a virus scanner for a group of tech-savvy engineers or a group of end users who are unlikely to be technically proficient?
Technical: How does the virus scanner work? What methods does it use to scan? How often are the .dat files updated? How quickly does the vendor respond to new virus threats and release new .dat files?
All of these factors must be considered when selecting antivirus solutions. Too often security experts simply recommend a product they are familiar with, without doing significant research.

## 8.4 Guided Exercise: Scanning for Viruses

## 8.5 Virus Infection and Identification

The unfortunate reality is that no matter what steps you take to prevent virus infections, there is still a chance your system being infected with a virus. The next question is, what do you do? Some facets of your response will depend upon the severity of the virus and how far it has spread, but generally, you need to focus on three things:

Stopping the spread of the virus.
Removing the virus.
Finding out how the infection started.
8.5.1 Stopping the Spread of the Virus
In the event of a virus infection, the first priority is to stop the spread of the infection. How this is done will, depend on how far the virus has spread. If the virus has only affected one machine, you can simply disconnect that machine from the network. However, it is unlikely that you will detect a virus before it has spread beyond a single machine. Given that fact, you will generally wish to follow these steps:

If the infection is on a segment of a WAN, then immediately disconnect from that WAN connection.
If the infection is on a subnetwork, immediately disconnect that subnetwork.
If there are servers with sensitive data that are connected (in any way) to the infected machine (or machines), disconnect those servers. This will prevent loss of sensitive data.
If there are backup devices connected to the infected machine or machines, disconnect them. This will prevent your backup media from becoming infected.
Obviously, your goal is to avoid getting a virus on your system. However, if that unfortunate event occur, following these steps can minimize the damage and get your system back up and functioning in a shorter period.

8.5.2 Removing the Virus
Once you have isolated the infected machine or machines, the next step is to clean them. If you know the specific virus, then you should be able to remove it by running an antivirus program, or you should be able to find virus removal instructions on the Internet. In the highly unlikely event that you cannot remove the virus, then you may have no other choice but to format the machine (or machines) and restore them from backups. However, it must be stressed that such a situation is very unlikely.

If you do successfully remove the virus, you will want to scan the machine thoroughly for any other virus infections before reconnecting it to your network. You should be certain it is completely clean before putting it back online.

8.5.3 Finding how the Infection Started
Once you have contained and removed the virus, the next goal is to see that it does not reappear. This is done by finding out how the virus got onto your system in the first place. To do this, you need to investigate the situation in three ways:

Talk to users of the infected machines and see if anyone opened any e-mail attachments, downloaded anything, or installed anything. Since these are the three most likely avenues for virus infection, they should be checked first.
Read any online documentation for that specific virus. It will tell you the normal method of propagation.
If neither of those avenues tells you what occurred, check any activity

8.6 Trojan Horses
A Trojan horse is an application that appears to have a benign purpose but actually performs some malicious function. This deception is what makes these applications a dangerous threat to your system. The Internet is full of useful utilities (including many security tools), screen savers, images, and documents. Most Internet users do download some of these things. Creating an attractive download that has a malicious payload is an effective way of gaining access to a person’s computer.

One defence against Trojan horses is to prevent all downloads, but that is not particularly practical. The value of the Internet is the easy access it provides to such a wide variety of information—restricting that access in such a draconian manner disrupts one of the most important reasons for giving employees Internet access. Instead of using such a heavy-handed tactic, you will learn other ways to protect your systems from Trojan horses.

Once you have a Trojan horse on your system, it may perform any number of unwanted activities. Some of the most common actions Trojan horses take include:

Erasing files on a computer.
Spreading other malware, such as viruses. Another term for a Trojan horse that does this is a dropper.
Using the host computer to launch distributed denial of service (DDoS) attacks or send spam.
Searching for personal information such as bank account data.
Installing a back door on a computer system. This means providing the creator of the Trojan horse easy access to the system, such as creating a username and password she can use to access the system.
Of the items on the above list, installing back doors and executing distributed denial of service attacks are probably the most frequent results of a Trojan horse attack, though installing spyware and dropping viruses are becoming much more common as well.

Below there is a list with some famous Trojan Horses:

Back Orifice
Anti-Spyware 2011
Shedun
Brain Test
FinFisher
NetBus
FlashBack
8.6.1 Trojan Horses Symptoms
It is difficult to determine whether your system is victim of a Trojan horse. There are a number of symptoms that might indicate that you have a Trojan horse. Assuming, of course, that you or another legitimate user are not making these changes, such symptoms include:

Home page for your browser changing
Any change to passwords, usernames, accounts, etc.
Any changes to screen savers, mouse settings, backgrounds, etc.
Any device (such as a CD door) seeming to work on its own
Any of these changes are symptoms of a Trojan horse and indicate your system is probably infected.


8.7 Spyware or Adware
Spyware is a growing problem both for home computer users and for organisations. There is, of course, the risk that such applications might compromise some sensitive information. Another problem of such applications is that they consume too much of your system’s resources. Spyware and adware both use memory. If your system has too many such applications, then they can consume so much of your system’s resources that your legitimate software will have trouble running. 

The primary difference between spyware and adware is what they do on your machine. They both infect your machine in the same manner. Spyware seeks to get information from your machine and make it available to some other person. This can be done in a number of ways. Adware seeks to create pop-up ads on your machine. Because these ads are not generated by the web browser, many traditional pop-up blockers will not stop them.

Both spyware and adware are growing problems for network security and home PC security. This is an important element of computer security software that was at one time largely ignored. Even today, not enough people take spyware seriously enough to guard against it. Some of these applications simply change your home page to a different site (these are known as home page hijackers); others add items to your favourites (or read items from them). Other applications can be even more intrusive.

Below there is a list with some famous spyware and adware:

Gator
RedSheriff
8.7.1 Anti-Spyware
Most antivirus products include anti-spyware. However, you can purchase dedicated anti-spyware software. Anti-spyware is an excellent way to defend against spyware and adware, just as antivirus software defends against viruses and Trojan horses. Essentially, it is software that scans your computer to check for spyware running on your machine. Most anti-spyware works by checking your system for known spyware files. It is difficult to identify specific activities that identify spyware, as you can with viruses. Each application must simply be checked against a list of known spyware. This means that you must maintain some sort of subscription service so that you can obtain routine updates to your spyware definition list.

In today’s Internet, running anti-spyware is as essential as running antivirus software. Failing to do so can lead to serious consequences. Personal data and perhaps sensitive business data can easily leak out of your organisation without your knowledge due to spyware. You should also keep in mind that it is entirely possible for spyware to be the vehicle for purposeful industrial espionage.