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

+




