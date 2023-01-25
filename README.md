# Configure a minecraft server on your own machine!

Simple steps to deploy minecraft server on linux machine. This instructions are sets in order to run minecraft server 1.19.3, with java 17

## Start by install linux environement
follow this documentations:
- [linux installation](./docs/linux-install.md) (docs/linux-install.md)
- [minecraft installation](./docs/minecraft-install.md) (docs/minecraft-install.md)

## Usage of commands
There is a main command `bash srvmng` used to manage severals actions on server instances. First argument is required. There is the list :

| Commands        | How to use           |
| :--- |:---|
| [Install](#install-the-command)| `srvmng --install` |
| [Check install](#check-the-installation) | `srvmng --checkInstall` |
| [Create](#create-a-instance) | `srvmng --create` |
| [Config](#configure-a-instance) | `srvmng --config` |
| [List](#list-all-instances) | `srvmng --list` |
| [Start](#start-an-instance) | `srvmng --start` |
| [Connect](#connect-to-an-instance) | `srvmng --connect` |
| [Remove](#remove-an-instance) | `srvmng --remove` |
| [Clear](#clear-all-instances) | `srvmng --clear` |
| [Help](#getting-help) | `srvmng --help` |

---

### Install the command
In order to install the command, use the flag `--install`
You can force the installation passing `force` to `--install` flag :
-  `srvmng --install`
-  `srvmng --install force`

Make file executable with `chmod +x srvcraft`
Then, add to your path (to use command like this `srvmng --create` instead of `bash srvmng --create`)

---

### Check the installation
In order to check if command is correctly installed, use the flag `--checkInstall`

Ex : `srvmng --checkInstall`

---

### Create a instance
To create a new instance, use the flag `--create`
You can pass parameters, in this order `srvmng --create[version] [servername] [memory]` :
- Version (in double quote : `srvmng --create "1.19.3"`)
- Server name (in double quote : `srvmng --create "1.19.3" "My server"`)
- Memory (in double quote : `srvmng --create "1.19.3" "My server" "2G"`)

Ex : `srvmng --create "1.19.3" "My Server" "1024M"`

---

### Configure a instance
To config the server.properties file from the desired instance, use the flag `--config`
Ex : `srvmng --config`

---

### List all Instances
To list all existing instances, use the flag `--list`

---

### Start an instance
To Start an existing instance, use the flag `--start`
You can pass parameters, in this order `srvmng --start [version] [servername] [memory]` :
- Version (in double quote : `srvmng --start "1.19.3"`)
- Server name (in double quote : `srvmng --start "1.19.3" "My server"`)
- Memory (in double quote : `srvmng --start "1.19.3" "My server" "2G"`)

Ex : `srvmng --start 1.19.3 "My Server" "1024M"`

---

### Connect to an instance
To connect to a running instance, use the flag `--connect`
It will ask you wich server do you want to connect.

Ex : `srvmng --connect`

---

### Remove an instance
To Remove a server folder or screen instance, use the flag `--remove`
It will ask you if you want to delete directory or screen.
Then ask wich server/screen have to be deleted

Ex : `srvmng --start 1.19.3 "My Server" "1024M"`

---

### Clear all Instances
To clear all existing instances, use the flag `--clear`

---

### Getting help
To show help message, use the flag `--help`


# References
- Installation of Java on ubuntu : https://tecadmin.net/install-latest-java-on-ubuntu/
- Customise prompt : https://scriptim.github.io/bash-prompt-generator/
- server.properties : https://minecraft.fandom.com/wiki/Server.properties
- Fandom tutorial : https://minecraft.fandom.com/wiki/Tutorials/Setting_up_a_server