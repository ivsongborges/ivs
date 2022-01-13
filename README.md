# Zoneminder em Ubuntu Server 20.04
 
 sudo apt upgrade
 
 sudo apt update
 
 sudo apt install mysql-server
 
 sudo add-apt-repository ppa:iconnor/zoneminder-1.36

 sudo apt update
 
 sudo apt install zoneminder
 
 mysql -uroot -p < /usr/share/zoneminder/db/zm_create.sql
 
 mysql -u root -p

CREATE USER 'zmuser'@localhost IDENTIFIED BY 'zmpass';

GRANT ALL PRIVILEGES ON zm.* TO 'zmuser'@'localhost' WITH GRANT OPTION;

FLUSH PRIVILEGES ;

quit

mysqladmin -uroot -p reload

*Configuring Zoneminder*


chmod 740 /etc/zm/zm.conf

chown root:www-data /etc/zm/zm.conf

adduser www-data video

a2enmod cgi

a2enconf zoneminder

a2enmod rewrite

a2enmod headers

a2enmod expires

*Starting Zoneminder and apache

    sudo systemctl enable zoneminder

    sudo service zoneminder start

    sudo service apache2 reload

Open zoneminder web console (http://localhost/zm/)
