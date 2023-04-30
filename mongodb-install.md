

$ apt-get install gnupg -y
$ wget -qO - https://www.mongodb.org/static/pgp/server-4.2.asc | apt-key add -  
$ echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu bionic/mongodb-org/4.2 multiverse" | tee /etc/apt/sources.list.d/mongodb-org-4.2.list  
$ apt-get update -y  
$ apt-get install mongodb-org -y  
$ sudo service mongod start
$ sudo service mongod status

http://localhost:27017


##### Install MongoDB client (Robo3T)

$ sudo snap install robo3t-snap

OR

Download from : https://linux.how2shout.com/how-to-install-robo-3t-on-ubuntu-22-04-lts-jammy-linux/

OR

$ wget https://download.robomongo.org/1.2.1/linux/robo3t-1.2.1-linux-x86_64-3e50a65.tar.gz  
$ tar -xvzf robo3t-1.2.1-linux-x86_64-3e50a65.tar.gz  
$ sudo mkdir /usr/local/bin/robo3t  
$ sudo mv  robo3t-1.2.1-linux-x86_64-3e50a65/* /usr/local/bin/robo3t  
$ cd /usr/local/bin/robo3t/bin  
$ sudo chmod +x robo3t ./robo3t  

$./robo3t

OR

Download Studio3t 
Downlodad Mongodb Compass
