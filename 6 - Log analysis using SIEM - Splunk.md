## 1. Understand the architecture of Splunk and the installation process. Setup collector and forwarder, then ensure the logs are accumulated in Splunk. Familiarize yourself with the dashboard fields.

Splunk is a software platform that enables organizations to collect, index, search, and analyze machine-generated data from various sources such as applications, servers, networks, and sensors.
Architecture of splunk consist of the following:
  - Forwarders: These are lightweight agents that run on the data source and collect data in real-time. The forwarders compress and encrypt the data before sending it to the indexer for processing.
  - Indexers: The indexers receive and store the incoming data from the forwarders. The indexers extract the metadata from the incoming data and create an index that allows users to search and retrieve data quickly.
  - Search heads: The search heads are web interfaces that allow users to interact with the data stored in the indexers. The search heads provide a search bar and a user interface for users to query the data, create reports and visualizations, and analyze the data in real-time.
  - Deployment server: The deployment server is a central management component that allows administrators to deploy and manage the configuration of the forwarders, indexers, and search heads across the Splunk infrastructure.
  - Cluster master: The cluster master is responsible for managing the indexing and search load across multiple indexers. The cluster master coordinates the replication and distribution of data across the indexers in the cluster.
  - Universal forwarders: Universal forwarders are lightweight agents that can be installed on any data source to collect and forward data to the indexers. Universal forwarders are optimized for high-volume data collection and can handle a variety of data sources.

#### Splunk-confiduration

  - First we have to get the IP and port of splunk enterprise.

![conf-splunk1](https://github.com/rahulr98/wireless-security/assets/116432525/ce551076-9ac7-4a25-b62c-40dc24f4ee9d)

  - Then give configure the splunk forwarder with the splunk enterprise.

![server conf1](https://github.com/rahulr98/wireless-security/assets/116432525/36fcc929-64bc-4270-a344-8cc52f10f267)

  - Now send a log to splunk enterprise.

![1](https://github.com/rahulr98/wireless-security/assets/116432525/56d037b9-32f9-4177-9d1c-cb077fe7e3cd)

## 2. Run Splunk >> Forwarder can be in the same system or another system (user’s convenience) >>Make sure the logs are indexing in the Splunk enterprise.• Run any network and port scanning commands from the host to the target machine. Run at least 5 to 8 commands. (If required, any tools can also be used).• Use the search section in Splunk to analyze the firewall logs to find the log of the above process and the exact IP from where the scan was performed. HINT: Use the “stats” command.• Analyze the log file and create an alert for any further similar activities ##

  - Now we perform a nmap-scan and save it as a log file
![1](https://github.com/rahulr98/wireless-security/assets/116432525/ec6f4c8a-c2ce-4e82-bca9-abc2b3ae5b49)

  - Now we have to send the logs to splunk
  - Now as a third person, we performs the command `scan` in splunk.
![4-1](https://github.com/rahulr98/wireless-security/assets/116432525/78b54f46-08ce-4a5b-9a56-d17f4cc09a7c)

  - If the index value is known to the person

![6-1](https://github.com/rahulr98/wireless-security/assets/116432525/d9ed5764-67df-4b72-a4d4-674f5df3cd02)

## 3. Run Splunk >> Forwarder can be in the same system or another system (user’s convenience) >>Make sure the logs are indexing in the Splunk enterprise.• Perform any communication using unencrypted traffic.• Use the Splunk search section to check the firewall logs to analyze which application uses unencrypted data. • Analyze the log file and create an alert for any further similar activities. ##

- First we visit a http site

![3 1](https://github.com/rahulr98/wireless-security/assets/116432525/3aec5efa-49c8-4831-86db-6f94987c9ea5)

- Now we add the location of the default logs of kali i.e /var/log into splunk.

![2023-05-15_12-47](https://github.com/rahulr98/wireless-security/assets/116432525/9d2657b5-4e37-45c6-8668-9deb796429ca)

- Now as a third person who only knowst that an unencrypted web traffic is being performed, we give a search of a http request in splunk.
![3 2](https://github.com/rahulr98/wireless-security/assets/116432525/deb0cb3d-4186-4e53-9e83-fb7711ecfd88)

- As we know, we perform a get request to access a website we can also give the following command.
![3 3](https://github.com/rahulr98/wireless-security/assets/116432525/9a673ba8-6f28-4e45-ba51-2412645be61a)

## 4. Run Splunk >> Forwarder can be in the same system or another system (user’s convenience) >>Make sure the logs are indexing in the Splunk enterprise. Download malware from this site. • After running your malware file, either it is stopped by your antivirus or not using the search section, find the antivirus log for the past 1 hour.• Run different malware files again in the same target system and use the search section to find the time range between the previous and current malware file execution. HINT: Use the “stats” command. • Then save that search as an alert to show a notification when the same type happens again.

## 5. Run Splunk >> Forwarder can be in the same system or another system (user’s convenience) >>Make sure the logs are indexing in the Splunk enterprise.• Logout of the target system and perform multiple failed attempts. Then use the search section to filter out the failed attempt logs. Hint: Use the “stats” command.• Analyze the log file and create an alert for any further similar activities.

  - We logout of the system and conduct multiple failed attempts.
 ![2023-05-16_00-43](https://github.com/rahulr98/wireless-security/assets/116432525/92210aee-4d66-4243-afba-d54dd88e96e0)

  - Now as a third person if we know only an authentication failure has happened,so the command can be
![2023-05-16_01-10_1](https://github.com/rahulr98/wireless-security/assets/116432525/8a1cc999-1d08-4117-94dc-9bcddd57058d)

  - or it can also be
![2023-05-16_01-11](https://github.com/rahulr98/wireless-security/assets/116432525/de6976d8-3368-4b89-840c-edba683b45c2)
