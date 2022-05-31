# RabbitMQ-Clustering-Ubunto
This repository will teach you how to set up a new Ubuntu Server with Docker and RabbitMQ Clustering. 



______________________________
First's Steps in Virtual Box |
------------------------------
1 - Crete a virtual machine;
2 - Go to VirtualBox settings -->  Network, put Adpter 1 Attached on Bridged Adapter, Now your server its like a one more machine in your network.

_________________________________________
First's Steps in Ubunto Virtual Machine |
-----------------------------------------
1 - Install NetTools.
> sudo apt install net-tools

2 -  Install OpenSSH.
> sudo apt install openssh-server

3 - Start SSH service.
> sudo ssh service start

4 - Grab Your machine ip.
> ifconfig

5 - Try connect into SSH on another machine in the same network;
> ssh serverName@serverIp

___________________________
 |Installing Docker Engine|
---------------------------
1 - Get updates.
> sudo apt-get update

2 - Install Updates
> sudo apt-get install \ ca-certificates \ curl \ gnupg \ lsb-release

3 - Add Directory To GPG (GNU Privacy Guard)
>  sudo mkdir -p /etc/apt/keyrings

4 - Add GPG (GNU Privacy Guard) Key
> curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

5 - Create Stable Directory
> echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

6 - Install Docker Engine.
> sudo apt-get update
> sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin

________________________________________________
 |Installing Docker Compose (TESTED IN V2.5.0) |
------------------------------------------------
1- Get Updates
> sudo apt-get update

2- Install Compose Plugin
> sudo apt-get install docker-compose-plugin
> sudo apt install docker-compose

3 - Verify version 
docker compose version

4 - Start afeter server startup
> sudo service docker start

_______________________
|Installing Erlang  |
-----------------------
1 - Adding Erlang to the repository manually
> wget https://packages.erlang-solutions.com/erlang-solutions_2.0_all.deb
> sudo dpkg -i erlang-solutions_2.0_all.deb


2 - Add Erlang public key to the apt-secure repository
> wget https://packages.erlang-solutions.com/ubuntu/erlang_solutions.asc
> sudo apt-key add erlang_solutions.asc

3 - Install
> sudo apt update
> sudo apt install erlang -y


_______________________________
|Installing RabbitMQ on Docker|
-------------------------------
1 - Clone this repository:
> https://github.com/ArthurHenriqueDalosto/rabbitMQ-Clustering-Ubunto-.git

2 - Give permission to startAll.sh
> sudo chmod +x startAll.sh

3 - Start
> sudo ./startAll.sh

______________
|Customizing |
--------------
If you want, you can open my script and my docker-compose.yml and edit if you need, you can change the password or username,
containers name, and Earlang cookie (Shared Key);


To acess RabbitQM Management Page, go to:
"yourserverip:8080"

username: admin
password: 123456




