# NET-LAB CISCO Commands Sheet

## Packet Tracer

**Features:**

-   Allows to create network topologies with Cisco devices and generic device;
-   Emulate the Command Line Interface (CLI) of the Cisco IOS (a subset of functions);
-   Allows to configure, using the CLI (or the GUI), the network devices so that to check the correctness of a network configuration;
-   Dynamically evaluate the device state and the traffic packets exchanged into the network;







### Terminals Modes

-   **User-EXEC-Mode** (`Name >`)  [***UEM***]:

    -   The User EXEC only allows for basic monitoring functions (“*view only*” mode) 

-   **Privileged-EXEC-Mode** (`Name #`)  [***PEM***]:

    -   Type `enable`  from *User-EXEC-Mode*  to get in  *Root-EXEC-Mode*;
    -   Type   `disable`   to get back in *User-EXEC-Mode*;

-   **Global-Configuration-Mode** (`Name (config)#`)  [***GCM***]: 

    -   Type  `configure terminal`  to get in this mode;
    -   Type  `exit`  or  `end`  or  `CTRL+Z`   to get back in *Privileged-EXEC-Mode*;  

-   **Interface-Configuration-Mode** (`Name (config-if)#`)  [***ICM***]:

    -   Type   `interface  vlan  1`   to enter in this mode;
    -   Type  `exit`  to get back in  *Global-Config-Mode*;
    -   Type  `end`  or  `CTRL+Z`  to get back in  *Privileged-EXEC-Mode*;

-   **ROM Monitor** (`>`):

    -   From *Privileged-EXEC-Mode*, use the  `reload`  EXEC command. Press the  ***Break***  key during the first 60 seconds while the system is booting.
    -   To exit ROM monitor mode, use the  `continue`  command.

    ![1552931263255](C:\Users\ivanf\AppData\Roaming\Typora\typora-user-images\1552931263255.png)









### Commands

-   `?`    -   help command;

-   `ena`  $\Leftrightarrow$  `enable` ;

-   `^`    -  shows the wrong part of the inserted command;

-   `hostname  new_hostname`  -  change hostname (***GCM***);

-   Configure a password for a specific console port:

    ```
    Router(config)#  line console 0
    Router(config-line)#  password <password>
    Router(config-line)#  login
    ```

-   Configure a password for the  *telnet*  access (*Virtual Terminal Line*):

    ```
    Router(config)#  line vty 0 4
    Router(config-line)#  password <password>
    Router(config-line)#  login
    
    ```

-   Configure a password for the *Privileged-EXEC-Mode*:

    1.  `enable  password  <my_password>`  (*not encrypted*);
        -   `service  password-encryption`  -  encrypts all the passwords;
    2.  `enable  secret  <my_psw>`  (*more robust encryption*);

-   `show` :

    -   “`show  interfaces`” – statistics about interfaces;
    -   “`show  controllers  serial`” – hardware level information about interfaces;
    -   “`show  clock`” – router clock;
    -   “`show  hosts`” – list of devices (*hostname* and *IP address*) known by the router;
    -   “`show  users`” – users connected to the router;
    -   “`show  history`” – list of commands used in the past;
    -   “`show  flash`” – information about flash memory and available IOS image files;
    -   “`show  version`” – hardware level features of the router and running IOS;
    -   “`show  ARP`” – ARP table of the router;
    -   “`show  protocol`” – *Layer 3* protocols configured at router level and at interface level;
    -   “`show  startup-configuration`” – startup configuration file (saved into the *NVRAM*);
    -   “`show  running-configuration`” – running configuration file (saved into the *RAM*);

-   `copy  running-config  startup-config`  -  save the actual configuration in the *NVRAM*;

-   `no  <command_name_to RollBack>`  -  rollback a specific executed command;

-   `copy  startup-config  running-config`  -  reload the startup config file from *NVRAM*;

-   Serial interface configuration:

    ```
    Router(config)#  interface  serial  0/0
    Router(config-if)#  ip  address  <ip_address>  <netmask>
    Router(config-if)#  clock  rate  56000   // just for serial interfaces         //
    Router(config-if)#  no  shutdown         // power UP physically the interfaces //
    ```

-   









### CISCO Routers

1.  CISCO [**4321**](https://www.cisco.com/c/en/us/support/routers/4321-integrated-services-router/model.html) (*Integrated Services Router*):
    ![1552902896175](C:\Users\ivanf\AppData\Roaming\Typora\typora-user-images\1552902896175.png)

    -   Series: *[Cisco 4000 Series Integrated Services Routers](https://www.cisco.com/c/en/us/support/routers/4000-series-integrated-services-routers-isr/tsd-products-support-series-home.html)* ;
    -   Released date: *30-SEP-2014*;
    -   The Cisco® 4000 Series Integrated Services Routers (ISRs) are designed for distributed organizations with multiple branch offices and remote sites. Today's branch offices offer full services through cloud, mobile, and multimedia applications, and require increased direct communication with both private data centers and public clouds across VPNs and the Internet. They also need a low total cost of ownership (TCO) for their networking hardware. 
        

2.  CISCO [**1941**](https://www.cisco.com/c/en/us/products/routers/1941-integrated-services-router-isr/index.html) (*Integrated Services Router*):
    ![1552902695594](C:\Users\ivanf\AppData\Roaming\Typora\typora-user-images\1552902695594.png)

    -   This product is no longer being sold.
    -   Suggested upgrade: *CISCO 4000 Series*;
        

3.  CISCO [**2901**](https://www.cisco.com/c/en/us/products/routers/2901-integrated-services-router-isr/index.html) (*Integrated Services Router*):
    ![img](C:\Users\ivanf\odrive\DRIVE MDA\__Univer__\Typora_Docs\NET_LAB\img\2901.jpg)

    -   This product is no longer being sold.
    -   Suggested upgrade: *CISCO 4000 Series*;
        

4.  CISCO [**2911**](https://www.cisco.com/c/en/us/products/routers/2911-integrated-services-router-isr/index.html) (*Integrated Services Router*):
    ![1552903298598](C:\Users\ivanf\AppData\Roaming\Typora\typora-user-images\1552903298598.png)

    -   This product is no longer being sold.
    -   Suggested upgrade: *CISCO 4000 Series*;
    -   The Cisco 2911 Integrated Services Router (ISR) delivers highly secure data, voice, video, and application service;
        

5.  CISCO [**819 IOx**](https://www.cisco.com/c/en/us/products/collateral/routers/800-series-routers/datasheet_C78-728353.html) (*Integrated Services Routers*):
    ![1552904164809](C:\Users\ivanf\AppData\Roaming\Typora\typora-user-images\1552904164809.png)

    -   With **3G** and **Wi-Fi** Data Sheet;

    -   The Cisco 819 ISR gateway provides a rapidly deployable, highly available, reliable, and secure solution designed specifically for machine-to-machine (M2M) applications.  Markets that benefit from these applications include industrial automation, transportation, financial, health care, utility, and retail. Fully integrated with Cisco IOS Software, the Cisco 819 family delivers, enterprise-class features, including highly secure data, voice, and video communications to stationary and mobile network nodes across wired and wireless links;
        

6.  CISCO [**819 HGW**]() (*Hardened Integrated Services Router*):
    ![1552904577140](C:\Users\ivanf\AppData\Roaming\Typora\typora-user-images\1552904577140.png)

    -   [Cisco 800 Series Routers](https://www.cisco.com/c/en/us/support/routers/800-series-routers/tsd-products-support-series-home.html);

    -   End-of-Sale: *22-SEP-2015*;
    -   End-of-Support_ *30-SEP-2020*;
        

7.  CISCO [**829**](https://www.cisco.com/c/en/us/products/routers/829-industrial-router/index.html)  (*Industrial Integrated Services Routers*):
    ![img](https://alln-extcloud-storage.cisco.com/ciscoblogs/IR829-dual-lte-550x266.png)

    -   829 Industrial Integrated Services Routers are compact, ruggedized, Cisco IOS Software routers with support for integrated **4G** LTE **wireless** **WAN** and **wireless LAN** capabilities.

8.  CISCO [**1240**](https://www.cisco.com/c/en/us/support/routers/1240-connected-grid-router/model.html#~tab-documents) (*Connected Grid Router*):

    -   [Cisco 1000 Series Connected Grid Routers](https://www.cisco.com/c/en/us/support/routers/1000-series-connected-grid-routers/tsd-products-support-series-home.html);

    -   Release Date: *22-NOV-2011*;
    -   Utilities and energy providers can now deploy rugged multi-service routers on secondary sub-stations, on pole tops and in other harsh environments.  Cisco 1000 Series Connected Grid Routers as key components of the **FAN** (Field Area Network) solution, offer a reliable communications platform for smart metering, distribution automation and remote workforce automation.
        

9.  CISCO [**1841**](https://www.cisco.com/c/en/us/obsolete/routers/cisco-1841-integrated-services-router.html) (*Integrated Services Router - Retirement Notification*):
    

    -   The Cisco 1841 ISR is now obsolete (past End-of-Life and End-of-Support status).
    -   Recommended: [Cisco 1921 ISR](https://www.cisco.com/c/en/us/support/routers/1921-integrated-services-router-isr/model.html);
        

10.  