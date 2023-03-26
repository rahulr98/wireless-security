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

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
**3. Perform DNS Spoofing attack using ARP Cache Poisoning attacks**

  - DNS spoofing involves redirecting trafiic from a ligitimate website to a fake one by modifying the DNS records that map a domain name to an IP address.
  - To perform Dos attack:
       - First, we have to create a website. Go to `/var/www/html` and edit *index.html*.
        
       ![dns5](https://user-images.githubusercontent.com/116432525/227776186-023e72d5-dd87-4226-87dd-850c4e6aa56b.png)
        
       - Then, 
