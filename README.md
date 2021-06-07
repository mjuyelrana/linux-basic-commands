# Linux-Basic-Command
Some Linux basic command for daily use


## **Install Full Webserver apache, php, mysql, phpmyadmin on ubuntu.**

0. **First Update** `sudo apt-get update`
1. **Install Apache** `sudo apt-get install apache2`
2. **Apache Config Test** `sudo apache2ctl configtest`
3. **Need to set server name** `sudo nano /etc/apache2/apache2.conf`
4. **Then need to paste `ServerName 127.0.0.1` at the last line of `apache2.conf` file**
5. **Restart the apache server `sudo systemctl restart apache2`**
6. **Set permission to folder access `sudo chmod 777 /var/www/html`**
7. **Install mysql** `sudo apt-get install mysql-server`
8. **Mysql security issues** `sudo mysql_secure_installation`
9. **Install php** `sudo apt-get install php libapache2-mod-php php-mcrypt php-mysql`
10. **Add Index.php file first** `sudo nano /etc/apache2/mods-enabled/dir.conf`
11. **Restart Apache for current changes** `sudo systemctl restart apache2`
12. **Install phpmyadmin** `sudo apt-get install phpmyadmin`
13. **Open the file `sudo nano /etc/apache2/apache2.conf` and this `Include /etc/phpmyadmin/apache.conf` paste
    to the last line of the file**.


**Note: if face problem in mysql_secure_installation**
0. `SHOW VARIABLES LIKE 'validate_password%';`
1. `SET GLOBAL validate_password.LENGTH = 4;`
2. `SET GLOBAL validate_password.policy = 0;`
3. `SET GLOBAL validate_password.mixed_case_count = 0;`
4. `SET GLOBAL validate_password.number_count = 0;`
5. `SET GLOBAL validate_password.special_char_count = 0;`
6. `SET GLOBAL validate_password.check_user_name = 0;`
7. `ALTER USER 'user'@'localhost' IDENTIFIED BY 'pass';`
8. `FLUSH PRIVILEGES;`

14. **Change the project location in `sudo nano /etc/apache2/sites-available/000-default.conf` to
    `DocumentRoot /home/juyel/www` then this command `sudo a2ensite 000-default.conf` and `sudo a2enmod rewrite`
    finally `sudo systemctl restart apache2`**



## **Some Linux Basic Command.**
1. **Upload file from local pc to server** `scp -r /path/to/my/files root@:0.0.0.0:/path/on/my/server`
2. **Unzip a zip file first** `sudo apt install unzip` then `unzip test.zip`
3. **Installing Node.js with Apt Using a NodeSource PPA**
    
   i. `curl -sL https://deb.nodesource.com/setup_14.x -o nodesource_setup.sh`

   ii. `nano nodesource_setup.sh` just see
   
   iii. `sudo bash nodesource_setup.sh` 

   iv. `sudo apt install nodejs`

15. **After add proxy to transfer http request to another port** `a2enmod proxy_http proxy headers session expires`

16. **Change Your default php version** `sudo update-alternatives --config php`
~~~~
There are 7 choices for the alternative php (providing /usr/bin/php).

  Selection    Path             Priority   Status
------------------------------------------------------------
  0            /usr/bin/php8.0   80        auto mode
  1            /usr/bin/php5.6   56        manual mode
  2            /usr/bin/php7.0   70        manual mode
* 3            /usr/bin/php7.1   71        manual mode
  4            /usr/bin/php7.2   72        manual mode
  5            /usr/bin/php7.3   73        manual mode
  6            /usr/bin/php7.4   74        manual mode
  7            /usr/bin/php8.0   80        manual mode

Press <enter> to keep the current choice[*], or type selection number: Here type the selection number and press enter
~~~~

17. **Install multiple version of php**
~~~~
sudo apt install php5.6 php5.6-fpm php5.6-mysql php5.6-sqlite3 php5.6-bcmath php5.6-gd php5.6-odbc php5.6-sybase php5.6-bz2 php5.6-gmp php5.6-opcache php5.6-tidy php5.6-cgi php5.6-imap php5.6-pgsql php5.6-xml php5.6-cli php5.6-interbase php5.6-phpdbg php5.6-xmlrpc php5.6-common php5.6-intl php5.6-pspell php5.6-xsl php5.6-curl php5.6-json php5.6-readline php5.6-zip php5.6-dba php5.6-ldap php5.6-recode php5.6-dev php5.6-mbstring php5.6-snmp php5.6-enchant php5.6-mcrypt php5.6-soap

sudo apt install php7.0 php7.0-fpm php7.0-mysql php7.0-sqlite3 php7.0-bcmath php7.0-gd php7.0-odbc php7.0-sybase php7.0-bz2 php7.0-gmp php7.0-opcache php7.0-tidy php7.0-cgi php7.0-imap php7.0-pgsql php7.0-xml php7.0-cli php7.0-interbase php7.0-phpdbg php7.0-xmlrpc php7.0-common php7.0-intl php7.0-pspell php7.0-xsl php7.0-curl php7.0-json php7.0-readline php7.0-zip php7.0-dba php7.0-ldap php7.0-recode php7.0-dev php7.0-mbstring php7.0-snmp php7.0-enchant php7.0-mcrypt php7.0-soap

sudo apt install php7.1 php7.1-fpm php7.1-mysql php7.1-sqlite3 php7.1-bcmath php7.1-gd php7.1-odbc php7.1-sybase php7.1-bz2 php7.1-gmp php7.1-opcache php7.1-tidy php7.1-cgi php7.1-imap php7.1-pgsql php7.1-xml php7.1-cli php7.1-interbase php7.1-phpdbg php7.1-xmlrpc php7.1-common php7.1-intl php7.1-pspell php7.1-xsl php7.1-curl php7.1-json php7.1-readline php7.1-zip php7.1-dba php7.1-ldap php7.1-recode php7.1-dev php7.1-mbstring php7.1-snmp php7.1-enchant php7.1-mcrypt php7.1-soap

sudo apt install php7.2 php7.2-fpm php7.2-mysql php7.2-sqlite3 php7.2-bcmath php7.2-gd php7.2-odbc php7.2-sybase php7.2-bz2 php7.2-gmp php7.2-opcache php7.2-tidy php7.2-cgi php7.2-imap php7.2-pgsql php7.2-xml php7.2-cli php7.2-interbase php7.2-phpdbg php7.2-xmlrpc php7.2-common php7.2-intl php7.2-pspell php7.2-xsl php7.2-curl php7.2-json php7.2-readline php7.2-zip php7.2-dba php7.2-ldap php7.2-recode php7.2-dev php7.2-mbstring php7.2-snmp php7.2-enchant php7.2-mcrypt php7.2-soap

sudo apt install php7.3 php7.3-fpm php7.3-mysql php7.3-sqlite3 php7.3-bcmath php7.3-gd php7.3-odbc php7.3-sybase php7.3-bz2 php7.3-gmp php7.3-opcache php7.3-tidy php7.3-cgi php7.3-imap php7.3-pgsql php7.3-xml php7.3-cli php7.3-interbase php7.3-phpdbg php7.3-xmlrpc php7.3-common php7.3-intl php7.3-pspell php7.3-xsl php7.3-curl php7.3-json php7.3-readline php7.3-zip php7.3-dba php7.3-ldap php7.3-recode php7.3-dev php7.3-mbstring php7.3-snmp php7.3-enchant php7.3-mcrypt php7.3-soap

sudo apt install php7.4 php7.4-fpm php7.4-mysql php7.4-sqlite3 php7.4-bcmath php7.4-gd php7.4-odbc php7.4-sybase php7.4-bz2 php7.4-gmp php7.4-opcache php7.4-tidy php7.4-cgi php7.4-imap php7.4-pgsql php7.4-xml php7.4-cli php7.4-interbase php7.4-phpdbg php7.4-xmlrpc php7.4-common php7.4-intl php7.4-pspell php7.4-xsl php7.4-curl php7.4-json php7.4-readline php7.4-zip php7.4-dba php7.4-ldap php7.4-dev php7.4-mbstring php7.4-snmp php7.4-enchant php7.4-mcrypt php7.4-soap

sudo apt install php8.0 php8.0-fpm php8.0-mysql php8.0-sqlite3 php8.0-bcmath php8.0-gd php8.0-odbc php8.0-sybase php8.0-bz2 php8.0-gmp php8.0-opcache php8.0-tidy php8.0-cgi php8.0-imap php8.0-pgsql php8.0-xml php8.0-cli php8.0-interbase php8.0-phpdbg php8.0-xmlrpc php8.0-common php8.0-intl php8.0-pspell php8.0-xsl php8.0-curl  php8.0-readline php8.0-zip php8.0-dba php8.0-ldap php8.0-dev php8.0-mbstring php8.0-snmp php8.0-enchant php8.0-mcrypt php8.0-soap

~~~~




   

