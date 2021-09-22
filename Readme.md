# GNS3
step1. Download DNS appliance on gns3.com <br  >
step2. Download Router on https://networkrare.com/free-download-cisco-ios-images-for-gns3-and-eve-ng/ <br  >
step3. Draw diagram as below <br  >
step4. Fix error dynamips : install dynamips:i386  <br  >
wget http://ppa.launchpad.net/gns3/ppa/ubuntu/pool/main/d/dynamips/dynamips_0.2.21-1~eoan1_i386.deb <br  >
dpkg -i dynamips_0.2.21-1~eoan1_i386.deb 



-----configure DNS Server--------------------- <br  >
step1. >nano /etc/hosts  <br  >
step2. add 192.168.122.200 fit.mta fit
       add 192.168.122.201 r1 
       add 192.168.122.202 r2 
step3. >service dnsmasq restart
       


------configure router---------------- <br  >
       (config)#conf t  <br  >
       (config)#host r1  <br  >
       (config-if)#int e1/1  <br  >
       (config-if)#no shut <br  >
       (config-if)#ip address 192.168.122.201 255.255.255.0 <br  >
       (config-if)#exit <br  >
       (config)#ip domain-lookup <br  >
       (config)#ip name-server 192.168.122.250  <br  >
       (config)#ip route 0.0.0.0 0.0.0.0 192.168.122.1 <br  >
       
------configure DNS client-------------- <br  >
       1. Open the terminal by pressing Ctrl + T

       2. Enter the following command to become the root user: su

       3. Once you’ve entered your root password, run these commands:

       rm -r /etc/resolv.conf
       nano /etc/resolv.conf

       4. When the text editor opens, type in the following lines:

       nameserver 192.168.122.250
       nameserver 8.8.8.8

       5. Close and save the file. You can do so by clicking Ctrl + X and pressing Y. Continue typing in the terminal:

       chattr +i /etc/resolv.conf
       reboot now
