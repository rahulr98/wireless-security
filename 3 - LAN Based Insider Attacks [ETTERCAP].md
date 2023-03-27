**ETTERCAP**

![image](https://user-images.githubusercontent.com/116432525/227794953-a48576cb-4523-4c81-bd57-c2c7d8b16216.png)

  - Ettercap is a powerfull network analysis tool that allows intercept, analyze, and manipulate network traffic in real-time, making it a useful tool for monitoring and troubleshooting network issues, as well as for conducting security assessments and penetration testing.
  - Some of the features of ettercap include:
      - Protocol analysis
      - Packet filtering
      - Man-in-the-middle attacks
      - Session hijacking
      - Password sniffing

----------------------------------------------------------------------------------------------------------------------------------------
**1. Perform Password stealing (over plaintext) using ARP Cache Poisoning attacks**
  
  - ARP cache poisining, also known as ARP spoofing, is a type of cyber attack where an attacker sends falsified ARP messages over a local network in order to associate the attacker's MAC adrress with IP address of another host on the network.
  - By doing so, the attacker can intercept and redirect network traffic intended for the targeted host to their own machine, allowing them to steal sensitive information like login creditials ans passwords.

   *Below fig shows that the task 1 is successfully completed.*
 ![1](https://user-images.githubusercontent.com/116432525/227773443-d72d3699-135e-4f13-84fc-5bcadb8d6968.png)
 
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
**2. Perform Denial of Service (DoS) attacks using ARP Cache Poisoning attacks.**

  - ARP cache poisining can also be used to carry out Denial of Service (Dos) attacks on a local network.
  - In a Dos attack, an attacker floods a target system with traffic in order to overwhelm it and cause it to be become unavailable to legitimate user.
  - Here, `Wireshark` is used to capture the traffics.

*Before the attack*
![dos1](https://user-images.githubusercontent.com/116432525/227775055-c1bfdcd1-b0b1-4bd2-8414-55534e4c1895.png)

*After the attack*
![Dos](https://user-images.githubusercontent.com/116432525/227774915-3fbd99ad-02b3-4bba-b1c8-1b9c2c825670.png)

*.pcap file is attached in Microsoft Teams*

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
**3. Perform DNS Spoofing attack using ARP Cache Poisoning attacks**

  - DNS spoofing involves redirecting trafiic from a ligitimate website to a fake one by modifying the DNS records that map a domain name to an IP address.
  - To perform Dos attack:
       - First, we have to create a website. Go to `/var/www/html` and edit *index.html*.
        
       ![dns5](https://user-images.githubusercontent.com/116432525/227776186-023e72d5-dd87-4226-87dd-850c4e6aa56b.png)
        
       - Then, go to `/etc/ettercap`, we can see two files named *etter.conf* and *etter.dns*.
       - From *etter.conf* change *ec_uid* and *ec_gid* value to 0,then scroll down to LINUX section and uncomment first two line and last two lines.

 *etter.conf* file:  
![dns3](https://user-images.githubusercontent.com/116432525/227793674-9f93de86-1a1b-4fff-a6b7-87bf03478d3b.png) 
![dns4](https://user-images.githubusercontent.com/116432525/227793680-f1484ef7-57a1-4fba-ad7b-3515f253e3df.png)
       
   - Then add the website(which we want to attack) domain and IP address.

![dns2](https://user-images.githubusercontent.com/116432525/227793876-88fcc89b-8cf3-4140-8b7a-9f7daa184637.png)
        
   - Finally open *ettercap* and start *ARP poisining* using *dns_spoof* plugin

![dns1](https://user-images.githubusercontent.com/116432525/227793993-8388dc17-6cf9-430a-9725-4c532ec09963.png)

 *Below image shows the result after attack.*
![dns](https://user-images.githubusercontent.com/116432525/227794011-9127adbf-49c1-4cff-994e-1a5709cd4922.png)

--------------------------------------------------------------------------------------------------------------------------------------------------------

**4. Invoke ‘sslstrip tool’ for stealing passwords from any machine that is connected to a LAN by stripping the HTTPS connection.**
  
   **SSLstrip -** It is a type of tool designed to demonstrate the effectiveness of HTTPS stripping attacks.
            - HTTPS stripping is a type of man-in-the-middle attack where the attacker intercepts the communication between a client and a server and downgrades the HTTPS connection to an unencrypted HTTP connection. This allows the attacker to view and modify the data being transmitted between the client and server.
            - SSLstrip works by intercepting HTTPS requests and redirecting them to HTTP requests. It then replaces all HTTPS links in the response with HTTP links, so the client continues to communicate with the server over an unencrypted connection. As a result, the attacker can see all the data transmitted between the client and server in plaintext.

![sslstrip](https://user-images.githubusercontent.com/116432525/228005659-e507c78a-d91d-413e-9e19-828f29a58993.png)

--------------------------------------------------------------------------------------------------------------------------------------------------------------

**5. Use arp_cop and scan_poisoner plugins to learn about the detection of ARP attacks.**

   **arp_cop -** It reports suspicious ARP activity by passively monitoring ARP requests/replies. It can report ARP posioning attempts, or simple IP-conflicts or IP-changes. If you build the initial host list the plugin will run more accurately.
   
![arp cop](https://user-images.githubusercontent.com/116432525/228008221-2215af98-c06a-4f4c-9709-43bc70646ec0.png)

  **scan_poisoner -** This plugin check if someone is poisoning between some host in the list and us.First of all it checks if two hosts in the list have the same mac address. It could mean that one of those is poisoning us pretending to be the other. It could generate many false-positives in a proxy-arp environment.

![scan poisoner](https://user-images.githubusercontent.com/116432525/228008938-68895543-6d99-4ed7-a51f-67ac48e34b70.png)

![arp poi2](https://user-images.githubusercontent.com/116432525/228009092-1cab1a12-5ff4-4a32-aef3-718fb60fd50b.png)

---------------------------------------------------------------------------------------------------------------------------------------------------------------------
