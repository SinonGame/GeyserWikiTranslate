Bedrock clients will join through Geyser and it will handle all the packet translations. There are four different versions of Geyser: Geyser for Bukkit (works on derivatives such as Spigot and Paper), Geyser for BungeeCord (also works on Waterfall), Geyser for Velocity, and Geyser Standalone. The first three versions run as plugins and can be installed directly onto the server. The standalone version can be used in a similar way, except you run it separately. 

If you are running a server, it is highly recommended you use one of the plugin versions, and if you want to join a server that does not have Geyser installed, you can run the standalone version. If you use Pterodactyl Panel we have an egg for the standalone version, please see [here](FAQ#can-i-use-geyser-with-pterodactyl-panel) for more information.

If you're still having problems with Geyser not working or giving you an "Unable to connect to world" error, see the [Common Issues](Common-Issues) page.\
For more information, take a look at the [Understanding the Config](Understanding-the-Config) page, and the [FAQ](FAQ) page.\
And if you still have questions, feel free to join the [Discord](https://discord.geysermc.org) if you haven't already.

## Plugin Setup
1. Download a jar of Geyser from the [build server](https://ci.nukkitx.com/job/Geyser/job/master/) depending on what platform your server runs on.
2. Put Geyser in your plugins folder and start up the server.
3. Configure any needed options in the Geyser config. A description of all options of the config can be found on the [Understanding the Config](https://github.com/GeyserMC/Geyser/wiki/Understanding-the-Config) page. In most scenarios, this file should not need to be touched unless you intend to use [Floodgate](Floodgate), or you're running your Java on a port that is not 25565. This may be the case if you are using a server hosting provider. Information on your hosting provider might be available on the [Supported Hosting Providers](https://github.com/GeyserMC/Geyser/wiki/Supported-Hosting-Providers) page. *You should not need to configure your remote address as the plugin handles this for you.*
4. Restart your server if needed.

Once you're done, open up Minecraft: Bedrock Edition and in the **Friends** tab, Geyser should show up there. If it does not show up, just add your IPv4 as an external server.

## Standalone Setup
Please keep in mind, you need some sort of computer or host to run Geyser Standalone on. Applications such as Termux on Android are capable of running Geyser, but this largely depends on how powerful your Android device is. Please do so at your own risk. Instructions to run Geyser on Termux can be found [here](Setup#termux-android).

1. Download a jar of Geyser from the [build server](https://ci.nukkitx.com/job/Geyser/job/master/).
2. Create a new folder for Geyser, and drop the jar in there.
3. Create a new bat or startup script, similar to the one you'd use for a Bukkit server, and take a look at [this](Creating-a-Startup-Script) page for what to put into it.
4. Run the startup script/bat, and all the necessary files for Geyser will be created.

Once you're done, open up Minecraft: Bedrock Edition and in the **Friends** tab, Geyser should show up there. If it does not show up, just add your IPv4 as an external server.

## Termux (Android)
Please read the disclaimer [here](Setup#standalone-setup) before continuing.
1. ~~Download Termux~~
2. ~~Follow [this guide](https://wiki.termux.com/wiki/Ubuntu)~~
3. ~~Run `apt install default-jre`~~
4. ~~Run `wget https://ci.nukkitx.com/job/GeyserMC/job/Geyser/job/master/lastSuccessfulBuild/artifact/bootstrap/standalone/target/Geyser.jar`~~
5. ~~Run `java -jar Geyser.jar`~~

~~OR~~

We have an automated setup script for clean Termux installs, might not work for all users. If the manual guide above does not work, try this.
Run this to start the download/install:
```
curl https://gist.githubusercontent.com/rtm516/e3e07d6595ee41e05a38b03c0f4d7a80/raw/install.sh | bash
```

## Setup Videos
Setup tutorials in a variety of languages.

### English
**Join Minecraft Java Servers From Bedrock Edition by [TehPiggeh](https://www.youtube.com/channel/UC-JJdyImQzJoRi1pcy654lQ)**

[![YouTube Video](https://img.youtube.com/vi/OmLxwl7_UzQ/0.jpg)](https://www.youtube.com/watch?v=OmLxwl7_UzQ)

**Connect to Java servers from Bedrock Edition! | GeyserMC Proxy Tutorial by [raimuakuna](https://www.youtube.com/channel/UCIMZsNCD_-prDETwRypAqmQ)**

[![YouTube Video](https://img.youtube.com/vi/7rwfScY66Jc/0.jpg)](https://www.youtube.com/watch?v=7rwfScY66Jc)

**How to play Java Servers in Minecraft Bedrock! by [PatarHD](https://www.youtube.com/channel/UCpowCAl4XV_hTQSYQpMWF6A)**

[![YouTube Video](https://img.youtube.com/vi/IHg_ts3MgLY/0.jpg)](https://www.youtube.com/watch?v=IHg_ts3MgLY)

**How to connect Bedrock players to Java servers Part One.** by [Casper](https://www.youtube.com/channel/UCHL0K3bOH0o7YoO5T-2_MzA)

[![YouTube Video](https://img.youtube.com/vi/DHZHM1RBtfQ/0.jpg)](https://www.youtube.com/watch?v=DHZHM1RBtfQ)

### Russian
**ЗАШЕЛ НА ХАЙПИКСЕЛЬ С МКПЕ? ЧИТЕРСКИЙ КОНФИГ!** by [TOWUK](https://www.youtube.com/channel/UCK8v-rGsfCOkpbi0slIpAng)
[![YouTube Video](https://img.youtube.com/vi/KcZZp05EfVQ/0.jpg)](https://www.youtube.com/watch?v=KcZZp05EfVQ)
