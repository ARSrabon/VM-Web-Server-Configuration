# VM-Web-Server-Configuration
How to configure VM Web Server.

**************** Install Apache Server ******************
Link: https://www.liquidweb.com/kb/how-to-install-apache-on-centos-7
Steps:
1. sudo yum -y update
2. sudo yum -y install httpd
3. sudo firewall-cmd --permanent --add-port=80/tcp
   sudo firewall-cmd --permanent --add-port=443/tcp
4. sudo firewall-cmd --reload
5. service httpd start // Start Apache server
6. service httpd status // View Apache Server Status
7. service httpd stop // Stop Apache Server
8. sudo systemctl enable httpd // To Start at boot
********************************************************

******************** Install PHP 7.1 *******************
Link: https://www.vultr.com/docs/how-to-install-php-7-x-on-centos-7
Steps:
1. sudo rpm -Uvh https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
2. sudo rpm -Uvh https://mirror.webtatic.com/yum/el7/webtatic-release.rpm
3. sudo yum install -y mod_php71w php71w-cli php71w-common php71w-gd php71w-mbstring php71w-mcrypt php71w-mysqlnd php71w-xml
4. sudo cp /etc/php.ini /etc/php.ini.bak
   sudo vi /etc/php.ini
5. sudo systemctl restart httpd.service // restart apache server after installing php
*******************************************************

******************* Install Latest Git ***************************
Link: https://stackoverflow.com/questions/21820715/how-to-install-latest-version-of-git-on-centos-6-x-7-x
1. yum install http://opensource.wandisco.com/centos/6/git/x86_64/wandisco-git-release-6-1.noarch.rpm
2. yum install git
3. git --version //to check installed git version.
*******************************************************

************** VMware NAT Port forwarding ****************
Link: https://kb.vmware.com/s/article/1018809 
Video: https://www.youtube.com/watch?v=3ZHGSqvwSQw
Steps: 
1. In the Workstation toolbar, click Edit > Virtual Network Editor to open the virtual network editor.
2. Select the network adapter that is set to the NAT interface, By default, this is VMnet8.
3.  Click the NAT Settings button.
4.  Click the Add button within the NAT Settings dialog box.
5.  In the Map Incoming Port dialog box, fill in these details:   
       *The host port needs to be an unused port. For example, you can use port 9997.
       *The virtual machine port needs to be 3389, unless you have changed it.
       *The virtual machine IP address needs to be the IP address assigned to the virtual machine you wish to connect to NAT connection.
6. Click OK.
************************************************************
