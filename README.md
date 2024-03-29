# eJPTv2-Lesson-1-Notes (all notes are for educational purposes)

Reconnaissance tool for Red teaming -- The tool gathers names, emails, IPs, subdomains, and URLs by using
multiple public resources.

theHarvester - github -- https://github.com/laramies/theHarvester
  Prepackaged with Kalilinux -- theHarvester -d hackersploit.org ib google,linkedin (example)
-- Can target domain and subdomains

haveibeenpwned.com (check if email or phone is in a data breach)

DNS (domain name system)
 - telephone directory that contains domain names and their corresponding IP addresses
 - Cloudfare (1.1.1.1) or Google (8.8.8.8)
DNS Records
 A - Resolves a hostname or domain to an IPv4 address
 AAAA - Resolves a hostname or domain to an IPv6 address
 NS - Reference to the domains nameserver.
 MX - Resolves a domain to a mail server.
 CNAME - Used for domain aliases.
 TXT - Text record.
 HINFO - Host information.
 SOA - Domain authority.
 SRV - Service records.
 PTR - Resolves an IP address to a hostname
 
 DNS Interrogation
 - + DNS interrogation is the process of enumerating DNS records for 
a specific domain.
+ The objective of DNS interrogation is to probe a DNS server to 
provide us with DNS records for a specific domain.
+ This process can provide with important information like the IP 
address of a domain, subdomains, mail server addresses etc

DNS Zone Transfer
+ In certain cases DNS server admins may want to copy or transfer 
zone files from one DNS server to another. This process is known 
as a zone transfer.
+ If misconfigured and left unsecured, this functionality can be 
abused by attackers to copy the zone file from the primary DNS 
server to another DNS server.
+ A DNS Zone transfer can provide penetration testers with a 
holistic view of an organization's network layout.
+ Furthermore, in certain cases, internal network addresses may be 
found on an organization's DNS servers.

![image](https://user-images.githubusercontent.com/90716060/227407156-36e7bbda-7f2f-4b3f-8eb7-a8bb699dcca4.png)

![image](https://user-images.githubusercontent.com/90716060/227407223-04891c62-031f-42ea-8666-105dbf322d2a.png)

Host Discovery With Nmap
![image](https://user-images.githubusercontent.com/90716060/227408103-2ee62a0e-4bd4-444c-9262-bbde0a4e5cc2.png)

Assessment Methodologies: Footprinting & Scanning

Scope: What will provide them value while not interfering with business. Physical access? VPN connection? What will the org provide. 

![image](https://user-images.githubusercontent.com/90716060/228408924-e916bf46-dd4a-447a-a491-ed0f2b13a278.png)

ARP: Address Resolution Protocol (RFC 826)
+ Resolve IP to MAC 
![image](https://user-images.githubusercontent.com/90716060/228409248-f08858b5-d1d6-4c1d-8d20-9f936b032f06.png)

Internet Control Message Protocol - If packets aren't making it somewhere. 
+ Traceroute/ping

Tools -- Wireshark/ARP-Scan/PING/FPING/NMAP/ZENMAP

Wireshark: Sudo arp-scan ![image](https://user-images.githubusercontent.com/90716060/228410226-09694db8-1fb4-4093-a242-4f316e250941.png)

ARP-SCAN
![image](https://user-images.githubusercontent.com/90716060/228410322-931f56b9-48c0-4138-af06-0b1f5bb5579c.png)

PING: Host unreachable ![image](https://user-images.githubusercontent.com/90716060/228410607-4e996b57-b44d-4144-a2dd-87e7036cf277.png)

FPING -- ![image](https://user-images.githubusercontent.com/90716060/228410775-d6c5f2fa-1c32-4775-8c06-5bdc940ab14a.png)
-a 2>/dev/null removes all error hosts that are unreachable through ICMP

NMAP: ![image](https://user-images.githubusercontent.com/90716060/228411204-90307775-fd93-4da9-9ed8-b28872eaec31.png)

ZENMAP: GUI version of nmap
+ ![image](https://user-images.githubusercontent.com/90716060/228411562-b6f113f9-c597-4b85-800a-466950a15cfc.png)

Port Scanning:
![image](https://user-images.githubusercontent.com/90716060/228412005-87fda04f-b374-4fdb-b8e3-4e3ace3646f8.png)

TCP handshake
![image](https://user-images.githubusercontent.com/90716060/228412042-b96fd848-cf2e-42c8-8882-ebf57ce2592a.png)
![image](https://user-images.githubusercontent.com/90716060/228412073-babba266-a0e6-46e0-9724-c149a1719405.png)
![image](https://user-images.githubusercontent.com/90716060/228412092-0fd4f523-a68a-418b-a58e-eb0bc951d172.png)
![image](https://user-images.githubusercontent.com/90716060/228412125-3a5c94a0-0e97-4784-87d6-2dbae3c13282.png)

![image](https://user-images.githubusercontent.com/90716060/229008879-ee0ab299-dac2-4caf-a66f-30357f5c92b1.png)

Scan the server:

Command ip a to find target inet/ip address
Ping target IP address >> nmap IP address >> 
nmap (IP address) -p-
![image](https://user-images.githubusercontent.com/90716060/230255170-c91933d1-73df-4f08-9bbf-37fdbf651561.png)
![image](https://user-images.githubusercontent.com/90716060/230255280-4bb9f4db-6984-4b0b-b3c1-c387e32d6b34.png)
![image](https://user-images.githubusercontent.com/90716060/230255316-6904f0bf-5d9e-4985-8aa4-f2e5c854e8ec.png)

Scan the server 2:
ip a to find IP address >> Ping IP >> nmap IP -p 1-250 >> One open port 177 >> nmap IP -p 177 -A (aggressive scan)
nmap IP -p 1-250 -sU (Scan UDP ports) >> 134/177/234 open >> nmap IP -p 134,177,234 -sUV >> ![image](https://user-images.githubusercontent.com/90716060/230256891-2658f3fc-0302-4f75-a379-8d3fb833294a.png)

nmap IP -p 134 -sUVC (UDP,Version,scripts) >> 134 hosting tftp server

Scan the server 3:
nmap IP -T4 (speed) >> nmap IP -T4 -p- >> nmap IP -T4 -sU (longer scan UDP, 161 open port) >> nmap IP -T4 -sU -p 161 -A >> ![image](https://user-images.githubusercontent.com/90716060/230258628-9b13d7d6-d5a5-4ba3-a149-6e4fb34bcaa7.png)


SMB: Server Message Block
- windows OS > ipconfig IP > nmap -t4 IP --open >> 135, 139, 445, 3389 open (Windows OS) 
- SMB hangs out at port 445 >> nmap IP -sV -o (what version of 445 SMB)
- nmap IP -sV -sC(default scripts) -- SMB Enumeration below
![image](https://user-images.githubusercontent.com/90716060/230527249-8e5bfb88-9f49-41a6-b56a-a4187caac838.png)
SMB is >> File explorer > MAP network drive >> IP from ipconfig >> Shows users, etc.
net use * /delete >> shows remote connections >> hit Y to remove mapped network drive
![image](https://user-images.githubusercontent.com/90716060/230527708-7422229d-c90a-400b-9c50-f97cbd74a423.png)
 Command will reappear network drive
 
 SMB: Nmap Scripts
 Ping >> Nmap IP >> 135, 139, 445 (smb) >> nmap -p445 (smb) --script smb-protocols IP >> 
 nmap -p445 --script smb-enum-sessions IP -- ![image](https://user-images.githubusercontent.com/90716060/230534501-4bde7a62-9f2c-4d92-9f29-259924e15be1.png)
- nmap -p445 --script smb-enum-sessions
- nmap -p445 --script smb-enum-shares IP 

