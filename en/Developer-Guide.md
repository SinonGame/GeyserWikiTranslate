## Compiling
1. Clone the repo to your computer (EG: `git clone https://github.com/GeyserMC/Geyser.git`)
2. [Install Maven](https://maven.apache.org/install.html)
3. Navigate to the Geyser root directory and run `git submodule update --init --recursive`. This downloads all the needed submodules for Geyser and is a crucial step in this process.
4. Run `mvn clean install` and locate to the `bootstrap`, then your desired Geyser version, then `target` folder.

## Project layout
* `bootstrap` is where we hold the specific platform code. So if you're porting Geyser to a new platform, you likely want to be in here.
* `common` is where some data types are and other parts used in other plugins such as Floodgate.
* `connector` is where connections are handled and the data conversion is done. If adding in some new packet conversions you likely want to be in here.

## Lombok
If you're using an IDE for editing any of the GeyserMC projects you will most likely need to install Project Lombok plugin as it is used to generate a bunch of handy functions. You can edit without it but you may get missing functions and or other issues displayed in your IDE. Please see the IDE section on their site for the supported plugins and install methods [https://projectlombok.org/setup/overview](https://projectlombok.org/setup/overview).

## wiki.vg
For a full rundown of the Java Edition protocol, see [here](https://wiki.vg/Protocol).

## wiki.vg (Bedrock)
The Bedrock Edition protocol is documented [here](https://wiki.vg/Bedrock_Protocol), but it's currently incomplete so only use it as a reference.

## ProxyPass
ProxyPass is a tool for intercepting packets between a Bedrock server and client developed by the NukkitX team. It can be found [here](https://github.com/NukkitX/ProxyPass) and the vanilla Bedrock server can be found [here](https://www.minecraft.net/en-us/download/server/bedrock/).

## MCC Toolchest
MCC Toolchest is a tool for viewing and editing NBT data for Bedrock edition, this allows you to see data as it is stored in Bedrock. You can download it from [here](http://mcctoolchest.com/).

## NBTExplorer
NBTExplorer is a tool for viewing and editing NBT data for Java edition, this allows you to see data as it is stored in Java edition. You can download it from [here](https://github.com/jaquadro/NBTExplorer/releases).


## pakkit
pakkit is a GUI based tool for intercepting packets between a Java edition server and client developed by our own [circuit10/Heath123](https://github.com/Heath123/) built using Electron. It also has experimental support for Bedrock Edition as a friendlier GUI wrapper for ProxyPass. You can download it from [here](https://github.com/Heath123/pakkit) under releases, or clone from GitHub for the latest version. It's currently WIP, so expect bugs.