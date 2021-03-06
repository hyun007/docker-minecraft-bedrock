# Minecraft Bedrock Server in Docker optimized for Unraid
This is a Basic Minecraft Bedrock Edition Server.
This container downloads Minecraft Bedrock Edition Server in the specified version or you can also set it to 'latest' to download and check on every restart if there is a newer version available.

UPDATE NOTICE: If you set the GAME_VERSION to 'latest' the container will check on every start/restart if there is a newer version available, otherwise enter the preferred version number that you want to install, you also can downgrade your server (no guarantee that it works if you downgrade much versions).

>**CONSOLE:** To connect to the console open up the terminal on the host machine and type in: 'docker exec -u minecraft -ti <Name of your Container> screen -xS Minecraft' (without quotes) to exit the screen session press CTRL+A and then CTRL+D or simply close the terminal window in the first place.

## Env params
| Name | Value | Example |
| --- | --- | --- |
| SERVER_DIR | Folder for gamefile | /serverdata/serverfiles |
| GAME_VERSION | Enter your preferred game version | latest |
| GAME_PARAMS | Extra startup Parameters if needed (leave empty if not needed) | |
| UID | User Identifier | 99 |
| GID | Group Identifier | 100 |

## Run example
```
docker run --name MinecraftBedrockServer -d \
	-p 19132:19132 -p 19132:19132/udp \
	--env 'GAME_VERSION=latest' \
	--env 'UID=99' \
	--env 'GID=100' \
	--volume /mnt/user/appdata/minecraftedrockserver:/serverdata/serverfiles \
	ich777/minecraftbedrockserver
```

This Docker was mainly edited for better use with Unraid, if you don't use Unraid you should definitely try it!

#### Support Thread: https://forums.unraid.net/topic/79530-support-ich777-gameserver-dockers/