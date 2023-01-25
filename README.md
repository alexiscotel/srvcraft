# Configure a minecraft server on your own machine!
Simple steps to deploy minecraft server on linux machine. This instructions are sets in order to run minecraft server 1.19.3, with java 17

## Start by install linux environement
follow this documentations:
- [linux installation](./docs/linux-install.md) (docs/linux-install.md)
- [minecraft installation](./docs/minecraft-install.md) (docs/minecraft-install.md)

## Usage of commands
There is a main command `bash srvmng` ([srvmng file](./srvmng)) used to manage severals actions on server instances. Arguments are required. there is the list :
-  `bash srvmng -i | --install` with `force` param optional (allow to re-install the command)
-  `bash srvmng -l | --list`
-  `bash srvmng -s | --start` with `[version] [servername] [memory]` optionals
-  `bash srvmng -d | --deploy` with `[version] [servername] [memory]` optionals
-  `bash srvmng --config` with `[version] [servername] [memory]` optionals
-  `bash srvmng --clear`
- `bash srvmng -h | --help`

### Install the command
In order to install the command, use the flag `--install` or use the command `bin/install` ([install file](./bin/install))
You can force the installation passing `force` to `--install` flag :
- `srvmng --install`
- `srvmng --install force`

Make file executable with `chmod +x srvcraft`
Then, add to your path (to use command like this `srvmng --create` instead of `bash srvmng --create`)


### List all Instances
To list all existing instances, use the flag `--list` or use the command `bin/list` ([list file](./bin/list))

### Start a instance
To Start an existing instance, use the flag `--start` or use the command `bin/start` ([start file](./bin/start))
You have to pass following parameters, **in order**:
- Version, required
- Server name, required too (in double quote : `bash bin/start 1.19.3 "My server"`)
- Memory (required a symbol of unit : M for megabyte, G for gegabyte, ...)

Ex : `srvmng --start 1.19.3 "My Server"`

### Create a instance
To create and deploy instance, use the flag `--deploy` or use the command `bin/deploy` ([deploy file](./bin/deploy)). You can pass following parameters:
- Version
- Server name (in double quote : `bash bin/start 1.19.3 "My server"`)
- Memory (required a symbol of unit : M for megabyte, G for gegabyte, ...)
- server.properties conf (only prompt questions)

Ex : `srvmng --deploy 1.19.3 "My Server" 1024M`

### config a server.properties file
To create and config a server.properties file, use the flag `--config` or use the command `bin/config` ([config file](./bin/config)). You can pass following parameters :
- Version
- Server name (in double quote : `bash bin/start 1.19.3 "My server"`)
- Memory (required a symbol of unit : M for megabyte, G for gegabyte, ...)

Ex : `srvmng --config 1.19.3 "My Server" 1024M`

### Clear all Instances
To clear all existing instances , use the flag `--clear` or use the command `bin/clear` ([clear file](./bin/clear)). 


# References
- Installation of Java on ubuntu : https://tecadmin.net/install-latest-java-on-ubuntu/
- Customise prompt : https://scriptim.github.io/bash-prompt-generator/
- server.properties : https://minecraft.fandom.com/wiki/Server.properties
- Fandom tutorial : https://minecraft.fandom.com/wiki/Tutorials/Setting_up_a_server