# GNS3
step1. Download DNS appliance on gns3.com
step2. Download Router on https://networkrare.com/free-download-cisco-ios-images-for-gns3-and-eve-ng/
step3. Draw diagram as below
step4. Fix error dynamips : install dynamips:i386 
wget http://ppa.launchpad.net/gns3/ppa/ubuntu/pool/main/d/dynamips/dynamips_0.2.21-1~eoan1_i386.deb

dpkg -i dynamips_0.2.21-1~eoan1_i386.deb



---configure DNS---
step1. >nano /etc/hosts
step2. add 192.168.122.200 fit1.mta fit1
           
