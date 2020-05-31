## 7.1 Configuring Windows

Properly configuring Windows (Windows 7, 8, 10 and Server Editions) consists of many facets. You must disable unnecessary services, properly configure the registry, enable the firewall, properly configure the browser, and more. 

Previously we have discussed the firewall concepts and the processes of both stateful packet inspection and stateless packet inspection, and a later section of this chapter discusses browser security. For now, let’s go over the other important factors in Windows security configuration.

### 7.1.1 Accounts, Users, Groups and Passwords

Any Windows system comes with certain default user accounts and groups. These can frequently be a starting point for intruders who want to crack passwords for those accounts and gain entrance onto a server or network. Simply renaming or disabling some of these default accounts can improve your security.

#### 7.1.1.1 Administrator Accounts

The default administrator account has administrative privileges, and hackers frequently seek to obtain logon information for an administrator account. Guessing a logon is a two-step process of first identifying the username, and then the password. Default accounts allow the hacker to bypass the first half of this process. Administrators should disable this account.

Some experts suggest simply renaming the administrator account, or using an administrator account that has a username that indicates its purpose. That is not a recommendation for the following reasons:

- The whole point is that a hacker should not be able to identify which username has administrative privileges.
- Simply renaming the administrator account to a different name, but one that still indicates its administrative rights will not help this situation.

#### 7.1.1.2 Other Accounts

The administrator account is the one most often targeted by hackers, but Windows also includes other default user accounts. Applying an equally demanding behaviour to all default accounts is a good idea. Any default account can be a gateway for a hacker to compromise a system. A few accounts that you should pay particular attention are:

- IUSR_Machine name: When you are running IIS, a default user account is created for IIS. Its name is IUSR_ and the name of your machine. This is a common account for a hacker to attempt to compromise. Altering this one in the manner suggested for the administrator account is advisable.
- ASP.NET: If your machine is running ASP.NET, a default account is created for web applications. A hacker that is familiar with .NET could target this account.
- Database accounts: Many relational database management systems, such as SQL Server, create default user accounts. An intruder, particularly one who wants to get at your data, could target these accounts.

When adding any new account, always give the new account’s user or group the least number and type of privileges needed to perform their job, even accounts for IT staff members. Below are some examples:

- A PC technician does not need administrative rights on the database server. Even though belongs to the IT department, does not need access to everything in that department.
- Managers may use applications that reside on a web server, but they certainly should not have rights on that server.
- Just because a programmer develops applications that run on a server does not mean that should have full rights on that server.

### 7.1.2 Setting Security Policies

Setting appropriate security policies is the next step in hardening a Windows server. This does not refer to written policies an organisation might have regarding security standards and procedures. In this case, the term security policies refers to the individual machines’ policies.

The first matter of concern is setting secure password policies. The default settings for Windows passwords are not secure. The table below shows the default password policies. Maximum password age refers to how long a password is effective before the user is forced to change that password. 

### 7.1.3 Account Lockout Policies

When you open the Local Security Settings dialog, your options are not limited to setting password policies. You can also set account lockout policies. These policies determine how many times a user can attempt to log in before being locked out, and for how long to lock them out. The default Windows settings are shown in the table below.


### 7.1.4 Registry Settings

The Windows Registry is a database used to store settings and options for Microsoft Windows operating systems. This database contains critical information and settings for all the hardware, software, users, and preferences on a particular computer. Whenever users are added, software is installed or any other change is made to the system (including security policies), that information is stored in the registry.

### 7.1.5 Registry Basics

The physical files that make up the registry are stored differently depending on which version of Windows you are using. Older versions of Windows (that is, Windows 95 and 98) kept the registry in two hidden files in your Windows directory, called USER.DAT and SYSTEM.DAT. In all versions of Windows since XP, the physical files that make up the registry are stored in %SystemRoot%\System32\Config. Since Windows 8, the file has been named ntuser.dat. 

### 7.1.6 Restrict Null Session Access

Null sessions are a significant weakness that can be exploited through the various shares that are on the computer. A null session is Windows’ way of designating anonymous connections. Any time you allow anonymous connections to any server, you are inviting significant security risks. Modify null session access to shares on the computer by adding RestrictNullSessAccess, a registry value that toggles null session shares on or off to determine whether the Server service restricts access to clients logged on to the system account without username and password authentication. Setting the value to “1” restricts null session access for unauthenticated users to all server pipes and shares except those listed in the NullSessionPipes and NullSessionShares entries.

### 7.1.7 Restrict Null Session Access Over Named Pipes

The null session access over named pipes registry setting should be changed for much the same reason as the preceding null session registry setting. Restricting such access helps to prevent unauthorised access over the network. To restrict null session access over named pipes and shared directories, edit the registry and delete the values, as shown below.

Key Path: HKLM\SYSTEM\CurrentControlSet\Services\LanmanServer

Action: Delete all values

### 7.1.8 Restrict Anonymous Access

The anonymous access registry setting allows anonymous users to list domain user names and enumerate share names. It should be shut off. The possible settings for this key are:

0—Allow anonymous users
1—Restrict anonymous users
2—Allow users with explicit anonymous permissions
Key Path: HKLM\SYSTEM\CurrentControlSet\Control\Lsa

Action: Set Value = 2

### 7.1.9 Remote Access to the Registry


Remote access to the registry is another potential opening for hackers. The Windows XP registry editing tools support remote access by default, but only administrators should have remote access to the registry. Fortunately, later versions of Windows turned this off by default. In fact, some experts advise that there should be no remote access to the registry for any person. This point is certainly debatable. If your administrators frequently need to remotely alter registry settings, then completely blocking remote access to them will cause a reduction in productivity of those administrators. However, completely blocking remote access to the registry is certainly more secure. To restrict network access to the registry:

1. Add the following key to the registry: HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurePipeServers\winreg.

2. Select winreg, click the Security menu, and then click Permissions.

3. Set the Administrator’s permission to Full Control, make sure no other users or groups are listed, and then click OK.

Recommended Value = 0

### 7.1.10 Services

A service is a program that runs without direct intervention by the computer user. In Unix/Linux environments, these are referred to as daemons. Many items on your computer are run as services. Internet Information Services, FTP Service, and many system services are good examples. Any running service is a potential starting point for a hacker. Obviously, you must have some services running for your computer to perform its required functions. However, there are services your machine does not use. If you are not using a service, it should be shut down.

### 7.1.11 Encrypting File System

This still exists in Windows 7, 8, and 10; however, with the later versions of Windows, EFS is only available in the upper-end editions of Windows such as Windows Professional. With this system, each file is encrypted using a randomly generated file encryption key, which is independent of a user’s public/private key pair; this method makes the encryption resistant to many forms of cryptoanalysis-based attacks. For our purposes the exact details of how EFS encryption works are not as important as the practical aspects of using it.

### 7.1.12 Security Templates

We have been discussing a number of ways for making a Windows system more secure, but exploring services, password settings, registry keys, and other tools can be a daunting task for the administrator who is new to security. Applying such settings to a host of machines can be a tedious task for even the most experienced administrator. 

The best way to simplify this aspect of operating system hardening is to use security templates. A security template contains hundreds of possible settings that can control a single or multiple computers. Security templates can control areas such as user rights, permissions, and password policies, and they enable administrators to deploy these settings centrally by means of Group Policy Objects (GPOs).

C:\Windows\Security\Templates folder. The following is a partial list of the security templates that you will find in this folder:

- Hisecdc.inf: This template is designed to increase the security and communications with domain controllers.
- Hisecws.inf: This template is designed to increase security and communications for client computers and member servers.
- Securedc.inf: This template is designed to increase the security and communications with domain controllers, but not to the level of the High Security DC security template.
- Securews.inf: This template is designed to increase security and communications for client computers and member servers.
- Setup security.inf: This template is designed to reapply the default security settings of a freshly installed computer. It can also be used to return a system that has been misconfigured to the default configuration.

## 7.2 Guided Exercise: Password Policies

## 7.3 Configuring Linux

An in-depth review of Linux security would be a lengthy task indeed. One reason is the diversity of Linux setups. Users could be using Debian, Red Hat, Ubuntu, or other Linux distributions. Some might be working from the shell, while others work from some graphical user interfaces such as KDE or GNOME. Fortunately, many of the same security concepts that apply to Windows can be applied to Linux. The only differences lie in the implementation, as explained in the following list:

- User and account policies should be set up the same in Linux as they are in Windows, with only a few minor differences. These differences are more a matter of using different names in Linux than in Windows. For example, Linux does not have an administrator account; it has a root account.
- All services (called daemons in Linux) not in use should be shut down.
- The browser must be configured securely.
- You must routinely patch the operating system.

### 7.3.1 Disable Services

Every service (daemon) that runs is executing code on the server. If there is a vulnerability within that code, it is a potential weakness that can be leveraged by an attacker; it is also consuming resources in the form of RAM and CPU cycles.

Many operating systems ship with a number of services enabled by default, many of which you may not use. These services should be disabled to reduce the attack surface on your servers. Of course you should not just start disabling services with reckless abandon—before disabling a service, it is prudent to ascertain exactly what it does and determine if you require it.

### 7.3.2 File Permissions

Most Unix/Linux file systems have a concept of permissions—that is, files which users and groups can read, write, or execute. Most also have the SETUID (set user ID upon execution) permission, which allows a nonroot user to execute a file with the permission of the owning user, typically root. This is because the normal operation of that command, even to a nonroot user, requires root privileges, such as su or sudo.

Typically, an operating system will set adequate file permissions on the system files during installation. However, as you create files and directories, permissions will be created according to your umask settings. As a general rule, the umask on a system should only be made more restrictive than the default. Cases where a less restrictive umask is required should be infrequent enough that chmod can be used to resolve the issue. Your umask settings can be viewed and edited using the umask command. See man umask1 for further detail on this topic.

### 7.3.3 File Integrity

File Integrity Management tools monitor key files on the file system and alert the administrator in the event that they change.These tools can be used to ensure that key system files are not tampered with, as in the case with a rootkit, and that files are not added to directories without the administrator’s permission, or configuration files modified, as can be the case with backdoors in web applications, for example.

There are both commercial tools and free/open source tools available through your preferred package management tool. Examples of open source tools that perform file integrity monitoring include Samhain and OSSEC. If you are looking to spend money to obtain extra features like providing integration with your existing management systems, there are also a number of commercial tools available.


### 7.3.4 Separate Disk Partitions

Disk partitions within Unix/Linux can be used not only to distribute the file system across several physical or logical partitions, but also to restrict certain types of action depending on which partition they are taking place on. Options can be placed on each mount point in /etc/fstab.

There are some minor differences between different flavours of Unix/Linux with regards to the options, and so consulting the system manual page—using man mount—before using options is recommended.

You can check for the location of setuid binaries using the following command:

- `$ sudo find / -perm -4000`
- 
Binaries that are specifically setuid root, as opposed to any setuid binary, can be located using the following variant:

- ` $ sudo find / -user root -perm -4000 `

### 7.3.5 Chroot

chroot alters the apparent root directory of a running process and any children processes. The most important aspect of this is that the process inside the chroot jail cannot access files outside of its new apparent root directory, which is particularly useful in the case of ensuring that a poorly configured or exploited service cannot access anything more than it needs to.

There are two ways in which chroot can be initiated:

The process in question can use the chroot system call and chroot itself voluntarily. Typically, these processes will contain chroot options within their configuration files, most notably allowing the user to set the new apparent root directory.


## 7.4 Guided Exercise: Linux File Permissions

## 7.5 Guided Exercise: Disabling Linux Services

- `netstat -tulpn`


## 7.6 Operating System Patches

From time to time, security flaws are found in operating systems. As software vendors become aware of flaws, they usually write corrections to their code, known as patches or updates. Whatever operating system you use, you must apply these patches as a matter of routine. 

Windows patches are probably the most well-known, but patches can be released for any operating system. You should patch your system any time a critical patch is released. You might consider scheduling a specific time simply to update patches. Some organisations find that updating once per quarter or even once per month is necessary.

### 7.6.1 Applying Patches

Applying patches means that the operating system, database management systems, development tools, Internet browsers, and so on are all checked for patches. In a Microsoft environment this should be easy because the Microsoft website has a utility that scans your system for any required patches to the browser, operating system, or office products. It is a very basic tenet of security to ensure that all patches are up-to-date. 

### 7.6.2 Automated Patch Systems

Manually patching machines can be quite cumbersome, and in larger networks, simply impractical. However, there are automated solutions that will patch all systems on your network. These solutions scan your systems at pre-set times and update any required patches.

### 7.6.3 Windows Update

For systems running Microsoft Windows, you can set up Windows to automatically patch your system. Recent versions of Windows have this turned on automatically. If your system is older, simply go to https://support.microsoft.com/en-us/help/12373/windows-update-faq and follow the instructions to keep your system updated. This will give that individual machine routing updates for the Windows operating system. 

This approach does have a few shortcomings, the first being that it will only update Windows and not any other applications on your machine. The second drawback is that it does not provide any way to check patches on a test machine before deploying them to the entire network. Its main advantages are that it is free, and integrated with the Windows operating system.

### 7.6.4 Unix/Linux Software Updates

Unlike Microsoft environments, Unix-based environments typically use a system of package management to install the majority of third-party applications.

Package management and update tools vary depending not only on which flavor of Unix you are running, but also differ depending on distribution you use. For example, Debian Linux and SUSE Linux use two different package management systems, and FreeBSD uses another.

#### 7.6.4.1 Core Operating System Updates

Many, but not all, UNIX systems have a delineation between the operating system and applications that are installed on it. As such, the method of keeping the operating system itself up-to-date will often differ from that of the applications. The method of upgrading will vary from operating system to operating system, but the upgrade methods fall into two broad bucket

