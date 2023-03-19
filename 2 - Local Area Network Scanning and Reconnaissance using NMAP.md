**A) Explain the subnet and use the NMAP Command to scan the services for the whole subnet.**
  - A subnet is a logical subdivision of an IP network, in which a single network address is divided into multiple sn=maller subnetworks.
  - Subnetting allows for more efficient use of IP address and can help to improve network performance and security by isolating different parts the network.
  - *Command using:*  `nmap -sV <IP>`

![1](https://user-images.githubusercontent.com/116432525/226199419-fce9368d-247c-41ce-8c77-99619d4e982a.png)

**B) What is a firewall and mention its types. Use the NMAP command to detect that a firewall protects 
the host**
  - A fire is a network security device that is designed to control and filter incoming and outgoing network traffic based on a set of predefined rules.
  - Its primary purpose is to protect networks and devices from unauthorized access, attacks, and malicious activity.
  - Firewalls can be implemented as software, hardware, or a combination of both. They work by examining the packets of network traffic and comparing them against the set of rules or policies defined by the administrator.
  - *Types of firewalls:* 
      - Packet-filtering firewalls.
      - Stateful inspection firewalls.
      - Application-level gateways (ALGs).
      - Next-generation firewalls (NGFWs).
 
 ![2](https://user-images.githubusercontent.com/116432525/226199763-a5a726cb-d74a-45b2-b01e-9aa96243d635.png)

**C) Use the NMAP command to scan a network and determine which devices are up and running.**
  
  ![3](https://user-images.githubusercontent.com/116432525/226200068-9b65ec97-fd50-40e7-9783-0761581c861f.png)

**D) What are vertical and horizontal scanning?**
  - *Vertical Scanning:*  It also known as deep scanning or comprehensive scanning, involves scanning a single device in great detail, with a focus on identifying as many open ports, services, and vulnerabilities as possible. Vertical scanning may involve multiple scanning techniques and may take longer to complete than horizontal scanning.
  - *Horizontal Scanning:*  It also known as wide scanning or network mapping, involves scanning multiple devices on a network to create a map of the network topology and identify which devices are active and which services are running on them. Horizontal scanning may involve a variety of scanning techniques and may take less time to complete than vertical scanning.

**E) Use the NMAP command to scan multiple hosts. [HINT: Add hosts into a file and scan it].**
  Add IP address to `/etc/hosts` file.
 
![4](https://user-images.githubusercontent.com/116432525/226200740-60f7d9d2-f700-4e3e-afca-4a7c17f76cdf.png)

![4a](https://user-images.githubusercontent.com/116432525/226200753-8dd89929-a9ae-4f8e-8c45-693d5bf6b0d2.png)

**F) Use NMAP commands to export the output in XML format.**
 
 ![image](https://user-images.githubusercontent.com/116432525/226203184-154a62d4-fe88-4c8b-b1df-863cc55c07a0.png)
 
 Here we used `-oX` flag.
 
 ![5](https://user-images.githubusercontent.com/116432525/226200911-c9fb3f68-0aab-46cb-8ad1-58979fb0dbb2.png)
 
 **G) Use the NMAP command to get OS information about a host.**
 
  Here we used `nmap -O <target-IP>` command.
 
 ![5](https://user-images.githubusercontent.com/116432525/226201089-3cdc24e9-9c21-443f-90b6-097adbf2fb84.png)
  
**H) Explain ping sweeping and Perform ping sweeping using Nma.**

  PING SWEEPING:  Ping sweeping is a network reconnaissance technique that involves sending a series of ICMP (Internet Control Message Protocol) echo request packets, commonly known as pings, to a range of IP addresses in order to determine which hosts are live and responding. This technique can be used to quickly identify the active hosts on a network, as well as to detect any potential issues with connectivity or network configuration.

![7](https://user-images.githubusercontent.com/116432525/226203254-f1e0f17c-0aa9-4cc3-bc5b-ca063a1fb9f8.png)

**I) What is a web application firewall? How do you use Nmap to detect a WAF? Perform WAF 
fingerprint detection using NMAP.**
  - A web application firewall (WAF) is a type of security tool that is designed to protect web applications from various types of attacks. A WAF works by analyzing incoming web traffic to identify and block malicious requests that could exploit vulnerabilities in the application.
  - A WAF operates at the application layer of the network stack, meaning that it can inspect the contents of incoming requests and responses in order to identify potentially malicious behavior. For example, a WAF might analyze the contents of a web request to look for SQL injection or cross-site scripting (XSS) attacks.
 
 To detect a WAF, we used nmap `-sV --script=http-waf-detect <target>` command.

![8](https://user-images.githubusercontent.com/116432525/226204417-98af8682-830b-4f4c-937f-cf2f064cce35.png)

To perform WAF fingerprint detection `nmap -sV --script=http-waf-fingerprint <target>`.

![9](https://user-images.githubusercontent.com/116432525/226204590-69dffdbc-91a8-4ca8-85bf-0ef045c0ccb2.png)

**J)  What is EXIF data? Try to find EXIF data of images on a website using NMAP NSE**
  
  - EXIF data (Exchangeable Image File Format) is metadata that is embedded in image files and contains information about the image, such as camera settings, date and time of creation, location, and other technical details.
  - The `http-exif-spider` script is a built-in Nmap script that is designed to crawl a website and extract EXIF data from image files. This script analyzes the response headers of each image file on the website and extracts any EXIF data that is present.

![10](https://user-images.githubusercontent.com/116432525/226205170-446b22e3-0bb7-4b29-85f6-76eb6d43b406.png)

**K)  Use NMAP NSE to find all subdomains of the website.**  
  - To use Nmap NSE to find all subdomains of a website, we can use the `dns-brute`.
 
  ![11](https://user-images.githubusercontent.com/116432525/226205623-141f649e-e0b3-49d9-9c58-24dec9c5a0bb.png)

**L)  Perform a vulnerability scan on the target host using NMAP NSE.**
   
   *Command:* `nmap -sV --script vuln <target>`.
  
 ![12](https://user-images.githubusercontent.com/116432525/226205827-4c47615e-cfee-485c-8aaf-5636534f3595.png)
