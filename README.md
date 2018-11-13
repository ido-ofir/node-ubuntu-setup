# node-ubuntu-setup

## ubuntu 16.4

1. install zsh if you want ( requires a restart )
```sh
apt-get install zsh
apt-get install git-core
wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | zsh
chsh -s `which zsh`
sudo shutdown -r 0
```

2. install node
```sh
curl -sL https://deb.nodesource.com/setup_11.x | sudo -E bash -
sudo apt-get install -y nodejs
sudo apt-get install -y build-essential
```

3. setup ubuntu firewall
```sh
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw allow ssh
sudo ufw allow http
sudo ufw allow https
sudo ufw enable
```

4. install <a href="https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/">mongodb</a> 
```sh
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 9DA31620334BD75D9DCB49F368818C72E52529D4
echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/4.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.0.list
sudo apt-get update
sudo apt-get install -y mongodb-org
sudo service mongod start
```


5. SSL encryption from <a htef="https://letsencrypt.org/">Let's Encrypt</a>
```sh
sudo apt-get install software-properties-common
sudo add-apt-repository ppa:certbot/certbot
sudo apt-get update
sudo apt-get install certbot
sudo certbot certonly --standalone -d [YOUR_DOMAIN_HERE]
```
