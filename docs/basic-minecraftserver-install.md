# Minecraft server preparation

this guide is based on the server.1.19.3.jar file from Mojang. Is work same with others versions.

## get files form minecraft server

Go to https://www.minecraft.net/en-us/download/server an copy link of minecraft_server.[version].jar
`
wget https://piston-data.mojang.com/v1/objects/c9df48efed58511cdd0213c56b9013a7b5c9ac1f/server.jar
`

Initialize directory with version (recommanded pattern: server-x.xx.x )
`
mkdir server-1.19.3
cd server-1.19.3
`


## Installation

Start installation of the server
`
java -Xmx1024M -Xms1024M -jar server.1.19.3.jar nogui
`

then edit eula.txt to accept terms (eula=true)
`
nano eula.txt
`

start in separate shell (not mandatory)
`
screen -S "Minecraft server"
`

start the server
`
java -Xmx1024M -Xms1024M -jar server.1.19.3.jar nogui
`

inside the server console, server responds with
`[Server thread/INFO]: Done (41.516s)! For help, type "help"`

press Ctrl+a+d to exit screen shell (``screen -r`` to reattach)


Installation completed and server running !
See ops.json for more configurations


## References
server.properties : https://minecraft.fandom.com/wiki/Server.properties
Fandom tutorial : https://minecraft.fandom.com/wiki/Tutorials/Setting_up_a_server