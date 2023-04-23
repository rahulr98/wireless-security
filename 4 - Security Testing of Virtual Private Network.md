# 1. Create an IPsec-based VPN with the help of the Strongswan tool. #
  **a)  Configure it with IKE version 1, perform the pen-testing procedures, and make it to IKE version 2 and follow the same. Add your observations to the report.**
  
  **MACHINE 1**-  10.0.2.15 DEVGATEWAY1.
  
  **MACHINE 2**-  10.0.2.4  DEVGATEWAY2.

  - We have to make some changes to `/etc/sysctl.conf`. Use `sysctl -p` command to see the changed settings.
  
![1](https://user-images.githubusercontent.com/116432525/233078760-9569832c-ad31-4167-92da-cb542233d663.png)

  - Now we have to change `/etc/ipsec.conf` in both matchines. Here *leftsubnet=*, _rightsubnet=_, and _Keyexchange=ikev1/2_ were changed.

  MACHINE 1:
  
 ```config setup
        charondebug="all"
        uniqueids=yes
conn devgateway1
        type=tunnel
        auto=start
        keyexchange=ikev1
        authby=secret
        left=10.0.2.15
        # leftsubnet=192.168.0.101/24
        right=10.0.2.4
        # rightsubnet=10.0.2.15/24
        ike=aes256-sha1-modp1024!
        esp=aes256-sha1!
        aggressive=no
        keyingtries=%forever
        ikelifetime=28800s
        lifetime=3600s
        dpddelay=30s
        dpdtimeout=120s
        dpdaction=restart
```
  
  MACHINE 2:
  
  ```config setup
        charondebug="all"
        uniqueids=yes
conn devgateway2
        type=tunnel
        auto=start
        keyexchange=ikev1
        authby=secret
        left=10.0.2.15
        # leftsubnet=192.168.0.101/24
        right=10.0.2.4
        # rightsubnet=10.0.2.15/24
        ike=aes256-sha1-modp1024!
        esp=aes256-sha1!
        aggressive=no
        keyingtries=%forever
        ikelifetime=28800s
        lifetime=3600s
        dpddelay=30s
        dpdtimeout=120s
        dpdaction=restart
   ```
   -   Next change `/etc/ipsec.secrets` file in both machines.
 
![2](https://user-images.githubusercontent.com/116432525/233082334-47c4733f-32dc-4bee-8894-bb5f4157c673.png)

   - Now ping the two machines to check if it is connected or not.

![3](https://user-images.githubusercontent.com/116432525/233082969-a6e2c88d-91f0-4e06-ade3-2610475a9eb0.png)

   -  Now using `ipsec up <gateway_name>`, establish the VPN between the two machines.

![4](https://user-images.githubusercontent.com/116432525/233083335-6e4a7584-a26b-4b2d-bc50-423a5408db50.png)

  Capture packets using wireshark.

![2023-04-19_18-36](https://user-images.githubusercontent.com/116432525/233084192-83b755a9-c056-4d4f-8c86-7eeee44ebd91.png)
