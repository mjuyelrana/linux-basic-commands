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



   

