1,from tooplate.com get a html page and launch in httpd service in centos
2,from tooplate.com get a html page and launch in Apache2,Mysql,LAMP,PHP wordpress service in ubuntu
3,automate the above 2 using provisioning
##############################################
commands used for centos:
switch to sudo
  1  vi /etc/hostname
    2  hostname finance
    3  cat /etc/hostname
    4  exit
    5  cat /etc/os-release
    6  yum install httpd wget vim unzip zip -y
    7  systemctl start httpd
    8  systemctl status httpd
    9  systemctl enable httpd
   10  systemctl status httpd
   11  ip addr show
   12  cd /var/www/html/
   13  ls
   14  touch index.html
   15  cd -
   16  ls
   17  pwd
   18  wget https://www.tooplate.com/zip-templates/2135_mini_finance.zip
   19  ls
   20  unzip -q 2135_mini_finance.zip
   21  ls
   22  cd 2135_mini_finance/
   23  ls
   24  cat 'ABOUT THIS TEMPLATE.txt'
   25  cp -R * /var/www/html/
   26  systemctl restart httpd
   27  vim /var/www/html/index.html
   28  echo "hello world" > /var/www/html/index.html
   29  systemctl restart httpd
   30  echo '<h1>heading 1 </h1>'  >> /var/www/html/index.html
   31  cat /var/www/html/index.html
   32  systemctl restart httpd
   33  ls
   34  cp index.html /var/www/html/
   35  systemctl restart httpd
   36  systemctl stop firewalld
   37  systemctl disable firewalld
   38  systemctl status firewalld
   39  history

  ############################################################################
  commands used in ubuntu :
  gone through the setup guide of word press and did in manually
Link:  
https://ubuntu.com/tutorials/install-and-configure-wordpress#1-overview

follow steps in docs
in mysql
CREATE DATABASE wordpress;
CREATE USER wordpress@localhost IDENTIFIED BY 'admin@123';
show databases;
GRANT SELECT,INSERT,UPDATE,DELETE,CREATE,DROP,ALTER ON wordpress.* TO wordpress@localhost;
FLUSH PRIVILEGES;
quit

sudo -u www-data cp /srv/www/wordpress/wp-config-sample.php /srv/www/wordpress/wp-config.php
sudo -u www-data sed -i 's/database_name_here/wordpress/' /srv/www/wordpress/wp-config.php
sudo -u www-data sed -i 's/username_here/wordpress/' /srv/www/wordpress/wp-config.php
sudo -u www-data sed -i 's/password_here/admin@123/' /srv/www/wordpress/wp-config.php

systemctl start apache2
ip addr show
launch 

##############################################################

provisioning :
##############################################################
check out the provisioned files



