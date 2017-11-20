# server-setup
Setting up an ubuntu server for web hosting

## Setup your user
* SSH into the server `ssh <username>@<server-ip>`
  * Follow the prompts and remember the password you set.
* Run `adduser <username>`
  * Give user sudo if need be `usermod -aG sudo <username>`

## Create an SSH key on your dev machine
* Run `ssh-keygen -t rsa` and follow the prompts.

## Add an SSH key to your user
* Run `ssh-copy-id <username>@<server-ip>` and enter your password when prompted.
### or do it manually


* `cat ~/.ssh/id_rsa.pub | ssh <username>@<server-ip> "mkdir -p ~/.ssh && cat >>  ~/.ssh/authorized_keys`
* Disable logging in with a password for your user `sudo vi /etc/ssh/sshd_config` find the `PermitRootLogin` line
* Change it to `PermitRootLogin without-password`

## Install nginx
* `sudo apt-get update && sudo apt-get upgrade -y`
* Install nginx `sudo apt-get install nginx -y`

## Install Git
* `sudo apt-get install git`

## Install Node
* `sudo apt-get install nodejs`
* `sudo apt-get install npm`
* `ln -s /usr/bin/nodejs /usr/bin/node`

## Get the servers private IP address
* There are multiple methods, will update this later.

## Install PM2 on the server
* `npm install pm2 -g`
