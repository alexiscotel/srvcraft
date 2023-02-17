
# Linux config (Debian 11.6 netinstall / Ubuntu 18.04)

## Debian fresh install configuration
apt install software-properties-common


## Users
To create user like root, add it to `sudo` and `adm` groups (have to be root for this command )
``
adduser <username>
addgroup <username> adm
addgroup <username> sudo
``

## Java

Start by install default jdk
```
sudo apt update
sudo apt install default-jdk
java -version
```

To let debian reach java ppa, it needed to pass an option to query the ubuntu server
``
apt-key adv --keyserver keyserver.ubuntu.com --recv-keys  C2518248EEA14886
``
Then, add the java repository
```
sudo add-apt-repository ppa:linuxuprising/java
sudo apt update
```

Then install the desired version
```
sudo apt install oracle-java17-installer
```
Set as Default
```
sudo apt install oracle-java17-set-default
java -version
```
check ENV vars
```
cat /etc/profile.d/jdk.sh 
```


## Screen
``
sudo apt install screen
``

Installation completed ! next : install.mincraft.md