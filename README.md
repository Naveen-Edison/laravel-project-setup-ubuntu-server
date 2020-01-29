# laravel-project-setup-ubuntu-server
Laravel Project Setup in Ubuntu Server 

# LARAVEL PROJECT SETUP IN UBUNRU SERVER : -
   

# SSH 
    ssh -i key root@11.11.111.111
    php my admin details are created copy the details : 
    url : localhost/phpmyadmin
    username :root
    Password: 123456

# CREATE USER 

    adduser demo (demo is project name)
    password : ? demo123
    re-enter pass : ? demo123 
    cd /home/demo/

# GIT CLONE REPOSITORY

    git clone 
    cd /demo(project folder)
    git branch
    git checkout develop(if develop branch)

# INSTALL COMPOSER

    apt install composer

# INSTALL CURL

    apt  install php7.0-curl 

# INSTALL ZIP 

    apt install zip
    composer update

# SETUP .ENV

    cp .env.example .env
    nano .env

# DATABASE CONNECTION

    DB_DATABASE=demo(set ur database table which you created in 
    phpmyadmin)
    DB_USERNAME=root(user name)
    DB_PASSWORD=123456(password) & save it .

    php artisan key:generate
    php artisan migrate --seed


# CONFIG IN UBUNTU SERVER
 
    cd /etc/apache2/sites-available/
    cp 000.default.conf demo.conf 
    nano demo.conf(set path for index page and set ip address or domain name)

    cd 

    sudo ln -sf /home/demo/demo/ /var/www/html/

    cd /home/demo/demo/

    sudo chgrp -R www-data storage bootstrap/cache public
    sudo chmod -R ug+rwx storage bootstrap/cache public

    chown -R www-data storage

# POSSPORT INSTALL FOR OAUTH

    php artisan passport:install

# PERMISSION FOR STORAGE PATH

    php artisan storage:link
    cd public/
    mkdir uploads
    chmod -R 777 uploads

    composer require league/oauth2-server:5.1.4

# ENABLE CONFIG IN SERVER
 
    sudo a2dissite 000-default.conf
    sudo a2ensite demo.conf

    sudo a2enmod rewrite 
    sudo service apache2 restart

#SWAP MEMORY: 
    https://www.digitalocean.com/community/tutorials/how-to-add-swap-space-on-ubuntu-16-04


#PERMISSION KEY : 
    sudo chgrp -R www-data storage bootstrap/cache public
    sudo chmod -R ug+rwx storage bootstrap/cache public

#FTP
    https://www.digitalocean.com/community/tutorials/how-to-set-up-vsftpd-for-a-user-s-directory-on-ubuntu-16-04


#Storage Error 
     sudo chown www-data:www-data storage/oauth-*.key
     sudo chmod 600 storage/oauth-*.key 
     sudo chmod 777 -R  resources/lang

#Curl Extension 
    sudo apt-get install php-curl
    sudo apt-get install php-mbstring

#Digital ocean droplet creation 
    https://www.digitalocean.com/community/tutorials/how-to-use-the-phpmyadmin-one-click-application-image#create-your-droplet
