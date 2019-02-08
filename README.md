# SQLMAP-Web-GUI
Before anything, this project wouldn't even be possible without the awesome development team behind SQLMAP - hats off to them!

This is a PHP Frontend I made to work with the SQLMAP JSON API Server (sqlmapapi.py) to allow for a Web GUI to drive near full functionality of SQLMAP!

Installattion

    sudo systemctl stop apache2 
    sudo apt-get install php php-pear libapache2-mod-python -y

    screen
    python /usr/share/sqlmap/sqlmapapi.py -s
    ctrl+shift+a+d

    sudo a2dissite 000-default.conf
    

Create SQLMAP-Web-GUI

    nano /etc/apache2/sites-available/kp1.conf

     <VirtualHost *:8080>
          ServerAdmin webmaster@example.com
          ServerName kp1
          ServerAlias kp1
          DocumentRoot /var/www/html/sqlmap
          ErrorLog /var/www/html/sqlmap/logs/error.log
          CustomLog /var/www/html/sqlmap/logs/access.log combined
     </VirtualHost>

Change port 80 to 8080 and 443 to 4443

    nano /etc/apache2/ports.conf

    cd /var/www/html/
    mkdir logs
    git clone https://github.com/4k4xs4pH1r3/SQLMAP-Web-GUI/
    
    sudo a2ensite kp1

    sudo systemctl start apache2
    sudo systemctl status apache2
    
Now you can open the SQLMAP-Web-GUI at http://kp1:8080
#
#
#
Here is a few quick videos I made to show that almost all of your usual SQLMAP command line functionality is still possible via this Web GUI. 

Demo against: Windows 2003 Server, IIS/6.0 + ASP + MS-SQL 2005
 - YOUTUBE: http://youtu.be/8MRew20Q1xE

Demo against: Linux (CentOS), Apache, MySQL, PHP
 - YOUTUBE: http://youtu.be/cs2Gvss0v-k

Blog Write-Up: http://kaoticcreations.blogspot.com/

Requirements:
 - Linux, Apache, PHP (check your favorite distro's wiki or forum pages, or use google)
   - PHP 5.3+ is suggested, older versions not tests so mileage may vary
 - Python and any SQLMAP dependencies (refer to their wiki for any help there)
 - Clone this repo to your machine
   - Edit the sqlmap/inc/config.php file so the paths all point to the right locations on your system
   - Copy the entire sqlmap/ directory and contents to your web root directory (cd SQLMAP-Web-GUI && cp -R sqlmap/ /var/www/)
   - When you want to use, simply fire up the sqlmap API server (python /home/user/tools/sqlmap/sqlmapapi.py -s)
   - Then you can navigate to the Web GUI address in your Browser to begin (firefox http://127.0.0.1/sqlmap/index.php)

Enjoy!

