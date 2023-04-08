# 1. Learn the basic working of Wi-Fi and its types with various types of attacks on it. #

   - Wi-Fi, short for Wireless Fidelity, is a wireless networking technology that allows devices to communicate with each other without the use of physical cables. Wi-Fi uses radio waves to transmit data between devices and access points, which are connected to a wired network.
   - There are several types of Wi-Fi networks, including:
      - **Wireless Personal Area Network (WPAN):**  WPAN is a short-range wireless network that typically covers a range of a few meters. Examples of WPAN technologies include Bluetooth and Near Field Communication (NFC).
      - **Wireless Local Area Network (WLAN):** WLAN is a wireless network that covers a larger area than WPAN, typically up to a few hundred meters. WLAN is commonly used in homes, offices, and public places such as airports, cafes, and libraries.
      - **Wireless Metropolitan Area Network (WMAN):**  WMAN is a wireless network that covers a larger area than WLAN, typically several kilometers. Examples of WMAN technologies include WiMAX and LTE.
      - **Wireless Wide Area Network (WWAN):**  WWAN is a wireless network that covers a very large area, typically spanning across countries or even continents. Examples of WWAN technologies include cellular networks such as 3G, 4G, and 5G.
   - Despite its convenience, Wi-Fi is susceptible to various types of attacks, including:
      - **Eavesdropping:** Eavesdropping involves intercepting and reading Wi-Fi traffic. This type of attack can be carried out using software such as packet sniffers.
      - **Man-in-the-Middle (MitM) attacks:** In a MitM attack, an attacker intercepts Wi-Fi traffic and alters it before forwarding it to its intended destination. This can allow the attacker to steal sensitive information such as login credentials.
      - **Rogue access points:** A rogue access point is an unauthorized Wi-Fi access point that is set up to mimic a legitimate access point. Users who connect to a rogue access point can unwittingly give an attacker access to their sensitive information.
      - **Denial of Service (DoS) attacks:** A DoS attack involves overwhelming a Wi-Fi network with traffic to the point that it becomes unavailable to legitimate users.
      - **Password cracking:** Password cracking involves using software to guess a Wi-Fi network's password. This can allow an attacker to gain access to the network and its connected devices.
   
# 2. Perform Wi-Fi fingerprinting using Wigile, Inssider, and Kismet. #

  **WiFi fingerprint-**   Wi-Fi fingerprinting is an approach to indoor asset tracking where the location and base station ID (BSSID) of each Wi-Fi access point (AP) in a building is recorded as part of a survey. An asset tag then scans the Wi-Fi environment and reports the list of Wi-Fi APs and their associated signal strengths.
  
  **WiGLE:**  
  
  ![wigle](https://user-images.githubusercontent.com/116432525/230715051-45698b20-4678-4b62-801c-c02fe37a2839.png)

   **inSSIDer:**  
   
   ![inssider](https://user-images.githubusercontent.com/116432525/230715639-fd63b9a1-6f96-4701-a785-d36bccb0a434.png)
   
   **Kismet:** 
      
   -  Turn on monitor mode of wifi card using this command `sudo airmon-ng start wlan0`.
      
   ![image](https://user-images.githubusercontent.com/116432525/230715780-47b69111-2fde-4e74-8bdc-7469ce2984b4.png)
      
   -  Then launch KISMET using this command `kismet -c wlanomon`.
   
   ![image](https://user-images.githubusercontent.com/116432525/230716317-e6e042fd-fb11-44f9-b860-f5b2f9219386.png)
   
   -  Go to localhost:2501 to view kismet page and create a account with custome password. Here, we created username= *kismet* and password= *kismet*.
   
   ![2023-04-08_16-01](https://user-images.githubusercontent.com/116432525/230716481-bf688d9b-5b85-4a9d-8881-95bc77001510.png)
   
   Here we can see the SSID and the different type of encryption used.
   
   ![23](https://user-images.githubusercontent.com/116432525/230716600-916e1668-2535-464c-ab6b-49e37ab1e8c1.png)
 
# 3. Create an Access point with any Wi-Fi encryption standard and start testing the security of that connection using any Wi-Fi security testing tools, which should include (Aircrack-Ng, Wifite, not limited). Try to capture the 4-way handshake using these methods. #

   - Start monitor mode using the command `airmon-ng start wlan0`.

   ![image](https://user-images.githubusercontent.com/116432525/230716829-6a771807-fd7f-41a5-bb5b-e68f13fa7217.png)
   
   - Now capture wireless traffic using `airdump-ng wlan0`.
   
   ![wq](https://user-images.githubusercontent.com/116432525/230717004-9b80890d-ecc8-458a-9e31-55ccb8d801bd.png)

   -  Use `airdump-ng --bssid EA:B0:9F:4A:50 -c 5 --write WPAcrack wlan0`, it will capture all the files include .pcap and store file to the present directory which can later be used for bruteforce the password.
   
   ![re](https://user-images.githubusercontent.com/116432525/230718583-94f75303-9356-4f04-8a3f-0a4dc560d1f5.png)

   -  Airplay-ng deauth `airplay-ng --deauth 100 -a EA:B0:9F:4A:50 wlan0`.
   
   ![ef](https://user-images.githubusercontent.com/116432525/230718702-8de73d30-737b-4b81-8b4c-9d697e260c77.png)
   
   -  4 way handshake during the deauth process.
   
   ![qwe](https://user-images.githubusercontent.com/116432525/230719364-7d38765a-7ce9-4c08-888d-efde3181a1b1.png)

# 4. After capturing the required files for testing, use dictionary generation and password 
cracking tools to crack the Wi-Fi password. 
a. You must use an existing word file to crack the password.
b. Also you have to create your dictionary file for cracking the passwords.
c. Keep 3 different types of passwords for your Wi-Fi to test it. Simple, medium, and 
complex passwords can be used for testing. Simple can be a dictionary word, 
medium can be of dictionary word with some numbers, and complex can be 
generated from any password generator online. #

   
