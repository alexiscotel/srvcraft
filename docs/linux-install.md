# Ubuntu server 18.04 configuration for minecraft server

## Create a new user
``
sudo -s 
adduser [user]
addgroup [user] sudo
addgroup [user] adm
``

## Prettier shell

### PSR1 prompt to add to the end of ~/.bashrc file

for users that can connect from outside (blue)
```
parse_git_branch() {
     git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1) /'
}
PS1='\[\e[0;2;38;5;251m\]\A\[\e[0m\] \[\e[0;3;38;5;33m\]\u\[\e[0;1m\]@\[\e[0;1;38;5;34m\]\H\[\e[0m\] \[\e[0;38;5;190m\]\w\[\e[0m\] \[\e[0;3;38;5;45m\]$(parse_git_branch)\[\e[0m\]'
```

for internal users (orange)
```
parse_git_branch() {
     git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1) /'
}
PS1='\[\e[0;2;38;5;251m\]\A\[\e[0m\] \[\e[0;38;5;178m\]\u\[\e[0;1m\]@\[\e[0;1;38;5;34m\]\H\[\e[0m\] \[\e[0;38;5;184m\]\w\[\e[0m\] \[\e[0;3;38;5;45m\]$(parse_git_branch)\[\e[0m\]'
```

for root (red blinking)
```
parse_git_branch() {
     git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1) /'
}
PS1='\[\e[0;38;5;251m\]\A\[\e[0m\] \[\e[0;1;5;38;5;160m\]\u\[\e[0;1m\]@\[\e[0;1;38;5;34m\]\H\[\e[0m\] \[\e[0;38;5;190m\]\w\[\e[0m\] \[\e[0;3;38;5;45m\]$(parse_git_branch)\[\e[0m\]'
```

## Java install

Start by install default jdk
```
sudo apt update
sudo apt install default-jdk
java -version
```

Add Java (Oracle) repository (accept terms)
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


## Screen install
``
sudo apt install screen
``
s
Installation completed ! next : install.mincraft.md


## References
Installation of Java on ubuntu  : https://tecadmin.net/install-latest-java-on-ubuntu/

Customise prompt : https://scriptim.github.io/bash-prompt-generator/