# Important to check those Versions while setting up the machine:

![image](https://github.com/meh-land/Tutorials/assets/79084467/3b8f53cd-ecaa-4255-9265-32e638a62264)
![image](https://github.com/meh-land/Tutorials/assets/79084467/39835ae7-cc0e-4b16-b5f6-27bf67243f4f)
![image](https://github.com/meh-land/Tutorials/assets/79084467/1edadf8a-69e5-4230-b970-9eab1eab302c)
![image](https://github.com/meh-land/Tutorials/assets/79084467/ee4cbf3d-4396-46dd-99bd-fe53d7c9ac4a)


# Step 1: Install Apache web server

1. Installing the Apache web server. For this purpose, enter the apache2 command:
```
sudo apt install apache2
```

2. After installing the Apache web server, you should see it running. If it doesn’t work for any reason, start Apache:
```
sudo systemctl start apache2
```

3. Then enter the following command to enable Apache at boot time:
```
sudo systemctl enable apache2
```

4. You can check the Apache status and make sure it is running without errors using the following command:
```
sudo systemctl status apache2
```

# Step 2: Install MySQL Server 

```
sudo apt install mysql-server
sudo mysql_secure_installation 
```

# Step 3: Install PHP8.1

1. Install Required Dependencies:

   First, you need to install the required build dependencies. Open a terminal and run the following command:
   ```
   sudo apt update
   sudo apt install -y build-essential libxml2-dev libsqlite3-dev curl libcurl4-openssl-dev pkg-config libssl-dev libonig-dev libzip-dev zlib1g-dev libpng-dev libjpeg-dev libfreetype6-dev libgmp-dev libpq-dev libicu-dev libbz2-dev libxpm-dev libwebp-dev libtidy-dev libxslt1-dev
   ```
2. Download PHP Source Code:
   ```
   wget https://www.php.net/distributions/php-8.1.0.tar.gz
   ```
3. Extract the Downloaded File:
   ```
   tar -xzf php-8.1.0.tar.gz
   ```
4. Configure the Build Environment:
   ```
   cd php-8.1.0
   ./configure --prefix=/usr/local/php --with-openssl --with-zlib --enable-bcmath --with-bz2 --enable-calendar --with-curl --enable-exif --enable-ftp --with-gd --enable-mbstring --with-mysqli --with-pdo-mysql --enable-soap --enable-sockets --enable-sysvsem --enable-sysvshm --enable-shmop --with-tidy --with-xmlrpc --with-xsl --enable-zip --with-pear --with-webp --with-jpeg --with-xpm --with-freetype --enable-intl
   ```

5. Compile and Install PHP:
```
make
sudo make install
```
6. Update System Path:
   ```
   echo 'export PATH="/usr/local/php/bin:$PATH"' >> ~/.bashrc
   source ~/.bashrc
   ```
7. Verify the Installation:
```
php -v
```

# Step 4:  Install Composer
```
curl -sS https://getcomposer.org/installer | php
sudo mv composer.phar /usr/local/bin/composer
composer --version
```

# Step 5:  Install Laravel10
```
composer global require laravel/installer
export PATH="$PATH:$HOME/.config/composer/vendor/bin"
```
# Step 6:  install npm v 8.11.0 and nodejs v- v16.15.1 

1. To install specific versions of Node.js and npm on Ubuntu 20.04, you can use the Node Version Manager (nvm). First, make sure you have curl installed:
```
sudo apt update
sudo apt install curl
```

2. Install nvm (Node Version Manager):
```
curl curl https://raw.githubusercontent.com/creationix/nvm/master/install.sh | bash
source ~/.bashrc
```

3. Check available Node.js versions with the following command:
```
nvm ls-remote
```
4. Install Node.js v16.15.1:
```
nvm install 16.15.1
nvm use 16.15.1
```

5. Install npm v8.11.0:
```
npm install -g npm@8.11.0
```

6. verify the installed Node.js and npm versions:
```
node -v
npm -v
```
# Step 7: Create mysql user for laravel API

1. Log in to MySQL as an administrative user:
```
sudo mysql
```
2. Create a new MySQL user with a username and password. Replace new_username and new_password with the desired username and password for the new user:
```
CREATE USER 'new_username'@'localhost' IDENTIFIED BY 'new_password';
GRANT ALL PRIVILEGES ON *.* TO 'username'@'localhost';
FLUSH PRIVILEGES;
EXIT;
```
# Step 8:  Clone Backend Repo. : [GP_laravel](https://github.com/meh-land/GP_laravel.git)
```
git clone https://github.com/meh-land/GP_laravel.git
cd GP_laravel
composer install
cp .env.example .env
```
* Open your .env file and change the database name (DB_DATABASE) to whatever you have, username (DB_USERNAME) and password (DB_PASSWORD) field correspond to your configuration.
![image](https://github.com/meh-land/Tutorials/assets/79084467/bf7d925a-c6c6-457a-ae82-bc5b0db58eac)

* if you are asked if u want to create DB tell yes.
```
php artisan key:generate
php artisan migrate
php artisan passport:install
php artisan serve --host=machine_IP
```
# Step 9:  Clone Frontend Repo. : [Dashboard](https://github.com/meh-land/Dashboard.git)
```
git clone https://github.com/meh-land/Dashboard.git
cd Dashboard
npm install
```
* add your local IP address in .env file
  ![image](https://github.com/meh-land/Tutorials/assets/79084467/cc6fe468-6648-41b7-be05-c1c60728b15f)

```
npm start
```


