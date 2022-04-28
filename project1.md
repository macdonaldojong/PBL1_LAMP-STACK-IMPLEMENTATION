
## **LAMP STACK IMPLEMENTATION**
*LAMP (Linux, Apache, MySQL, PHP or Python, or Perl)*.

# *STEP1: INSTALLING APACHE AND UPDATING THE FIREWALL*.

![lunch aws instance](./images/Aws%20Instance%20running.PNG)

**Update a list of packages in package manager**.

`sudo apt update`

**run apache2 package installation**

`sudo apt install apache2`

![apahe running](./images/Apache%20set%20an%20running.PNG)

**http://52.53.124.37:80**.

![instance public ip](./images/Aws%20instance%20Public%20address.PNG)

![apache set and running](./images/Apache%20set%20and%20running.PNG)

## *STEP 2 — INSTALLING MYSQL*

`sudo apt install mysql-server`

![install mysql](./images/mySQL%20install%20and%20running.PNG)

**validate password:**
`sudo mysql_secure_installation`

## *STEP 3 — INSTALLING PHP*
**To install these 3 packages at once, run:**
`sudo apt install php libapache2-mod-php php-mysql`

**confirm your PHP version:**

`Php –v`

![install php](./images/PHP%20install.PNG)


**At this point, your LAMP stack is completely installed and fully operational.**

•Linux (Ubuntu)
•Apache HTTP Server
•MySQL
•PHP

# *STEP 4 — CREATING A VIRTUAL HOST FOR YOUR WEBSITE USING APACHE*

**You can now use a2ensite command to enable the new virtual host:**

![see a2ensite on site](./images/php%20on%20the%20link.PNG)

`sudo a2ensite projectlamp`

`sudo systemctl reload apache2`


# STEP 5 — ENABLE PHP ON THE WEBSITE

`sudo vim /etc/apache2/mods-enabled/dir.conf`

**Edit the /etc/apache2/mods-enabled/dir.conf file and change the order in which the index.php file is listed within the DirectoryIndex directive:**

<IfModule mod_dir.c>
        #Change this:
        #DirectoryIndex index.html index.cgi index.pl index.php index.xhtml index.htm
        #To this:
        DirectoryIndex index.php index.html index.cgi index.pl index.xhtml index.htm
</IfModule>

`sudo systemctl reload apache2`

`sudo apt-get install libapache2-mod-php5`

`sudo vim /var/www/projectlamp/index.php`

**insert the following below, save and close**

<?php
phpinfo();
?>

**Testing PHP Processing on your Web Server:**

![PHP running](./images/PHP%20running.PNG)

**Lastly, to remove the project, run the code below**:
`sudo rm /var/www/projectlamp/index.php`