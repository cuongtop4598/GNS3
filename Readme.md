# GNS3
step1. Download DNS appliance on gns3.com <br  >
step2. Download Router on https://networkrare.com/free-download-cisco-ios-images-for-gns3-and-eve-ng/ <br  >
step3. Draw diagram as below <br  >
step4. Fix error dynamips : install dynamips:i386  <br  >
wget http://ppa.launchpad.net/gns3/ppa/ubuntu/pool/main/d/dynamips/dynamips_0.2.21-1~eoan1_i386.deb <br  >
dpkg -i dynamips_0.2.21-1~eoan1_i386.deb 



-----configure DNS--------------------- <br  >
step1. >nano /etc/hosts  <br  >
step2. add 192.168.122.200 fit.mta fit
       add 192.168.122.201 r1 
       add 192.168.122.202 r2 
step3. >service dnsmasq restart
       


------configure router---------------- <br  >
       (config)#conf t
       (config)#host r1
       (config-if)#int e1/1
       (config-if)#no shut
       (config-if)#ip address 192.168.122.201 255.255.255.0
       (config-if)#exit
       (config)#ip domain-lookup
       (config)#ip name-server 192.168.122.250 
       (config)#ip route 0.0.0.0 0.0.0.0 192.168.122.1
       
