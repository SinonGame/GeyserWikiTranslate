This page covers basic information about the Geyser config and what each option does. Though they are explained in the configuration itself, this explains what each option does in more detail.

## Bedrock Section
The options for Geyser on the bedrock-facing end. Mostly contains options for how bedrock edition will see the server.

**`address`**: The address of Geyser on the bedrock end. In most all scenarios, this should not need to be changed.

**`port`**: The port Geyser will run on. By default, it is 19132 in bedrock.

**`motd1`**: The first line of the MOTD for Geyser. 

**`motd2`**: The second line of the MOTD for Geyser. **Please keep in mind, this option will only work if Geyser is shown in the Friends tab!**

## Remote Section
Options for the remote (java) server. 

*The following two configuration options do not generally apply for plugin versions as the plugin handles connecting to the running server.*

**`address`**: The address of the Minecraft: Java Edition server you want to join.

**`port`**: The port of the Minecraft: Java Edition server you specified in the `address` section.

**`auth-type`**: The authentication type of the Minecraft: Java Edition server. Valid options are `online`, `offline`, and `floodgate`.

**Please keep in mind, what you specify in the Geyser `auth-type` option MUST be the same as what the remote server has (with the exception of Geyser being in online mode and remote being in offline mode). You simply cannot join an online mode server without a genuine account. If you want to allow Minecraft: Bedrock Edition accounts to join without a Minecraft: Java Edition account, see the [Floodgate](Floodgate) page.**

## General Options
General Geyser options that are mostly specific to Geyser itself.

**`floodgate-key-file`**: The key file path for Floodgate. Requires that you have [Floodgate](https://github.com/GeyserMC/Floodgate) installed and the `auth-type` set to `floodgate`.

**`userAuths`**: A section where you can put the authentication information for your Minecraft: Java Edition account for immediate login when joining Geyser. **It is advised you ONLY use this option if you are running Geyser locally and that ONLY you have access to the config as it requires you put your Minecraft: Java Edition credentials in plain text!**

If your Xbox account name was Notch, your Java email was `foobar2000@gmail.com` and your password was `hunter2`, you would fill this into the config:

```
userAuths:
  Notch: # MCPE/Xbox username
    email: foobar2000@gmail.com
    password: "hunter2"
```

**`command-suggestions`**: Bedrock clients freeze or crash when opening up the command prompt for the first time with a large amount of command suggestions. This config option disables command suggestions being sent to prevent any freezing.

**`passthrough-motd`**: If the MOTD should be relayed from the remote server. Causes the `motd1` and `motd2` options in the bedrock section to no longer have a use.

**`passthrough-players`**: If the current and max player counts should be relayed from the remote server.

**`legacy-ping-passthrough`**: If enabled, manually pings the server by impersonating a Minecraft client instead of using the server's API. **This option should *only* be enabled if your MOTD or player count is not accurate,** as it can cause errors especially on BungeeCord. This option does nothing on standalone.

**`ping-passthrough-interval`**: How often the fake Minecraft client should attempt to ping the remote server to update information, in seconds (a setting of 1 will ping the server every second; a setting of 3 will ping the server every three seconds). Only relevant for standalone and legacy ping passthrough. Increase the number if you're getting timeout or BrokenPipe exceptions.

**`max-players`**: The maximum amount of players that can join through Geyser.

**`debug-mode`**: If debug messages should be printed in console. Useful if you run into an error and need more context.

**`general-thread-pool`**: The amount of threads Geyser will be able to use. Higher is not always better :P.
 
**`allow-third-party-capes`**: If third party (Optifine, 5zig, LabyMod, etc.) capes should be displayed to the bedrock player.

**`allow-third-party-ears`**: If third party Deadmau5-style ears should be enabled. Currently only supports MinecraftCapes.

**`default-locale`**: The default locale to send to players if their locale could not be found. Check this page https://github.com/GeyserMC/Geyser/wiki/FAQ#what-languages-does-geyser-support to find the code corresponding to your language.

**`chunk-caching`**: Cache chunks for each Bedrock player and adds support for additional sounds at the expense of more RAM usage. This option is always on for Bukkit as we can use the server's API to get block information at no expense.

**`above-nether-bedrock-building`**: Bedrock prevents building and displaying blocks above Y127 in the Nether - enabling this config option works around that by changing the Nether dimension ID to the End ID. The main downside to this is that the sky will resemble that of the End sky in the Nether, but ultimately it's the only way for this feature to work.

Default Geyser Config:
```yml
# --------------------------------
# Geyser Configuration File
#
# A bridge between Minecraft: Bedrock Edition and Minecraft: Java Edition.
#
# GitHub: https://github.com/GeyserMC/Geyser
# Discord: https://discord.geysermc.org/
# --------------------------------

bedrock:
  # The IP address that will listen for connections
  address: 0.0.0.0
  # The port that will listen for connections
  port: 19132
  # The MOTD that will be broadcasted to Minecraft: Bedrock Edition clients. Irrelevant if "passthrough-motd" is set to true
  motd1: "GeyserMC"
  motd2: "Another GeyserMC forced host."
remote:
  # The IP address of the remote (Java Edition) server
  address: 127.0.0.1
  # The port of the remote (Java Edition) server
  port: 25565
  # Authentication type. Can be offline, online, or floodgate (see https://github.com/GeyserMC/Geyser/wiki/Floodgate).
  auth-type: online

# Floodgate uses encryption to ensure use from authorised sources.
# This should point to the public key generated by Floodgate (Bungee or CraftBukkit)
# You can ignore this when not using Floodgate.
floodgate-key-file: public-key.pem

## the Xbox/MCPE username is the key for the Java server auth-info
## this allows automatic configuration/login to the remote Java server
## if you are brave/stupid enough to put your Mojang account info into
## a config file
#userAuths:
#  bluerkelp2: # MCPE/Xbox username
#    email: not_really_my_email_address_mr_minecrafter53267@gmail.com # Mojang account email address
#    password: "this isn't really my password"
#
#  herpderp40300499303040503030300500293858393589:
#    email: herpderp@derpherp.com
#    password: dooooo

# Bedrock clients can freeze when opening up the command prompt for the first time if given a lot of commands.
# Disabling this will prevent command suggestions from being sent and solve freezing for Bedrock clients.
command-suggestions: true

# The following two options enable "ping passthrough" - the MOTD and/or player count gets retrieved from the Java server.
# Relay the MOTD from the remote server to Bedrock players.
passthrough-motd: false
# Relay the player count and max players from the remote server to Bedrock players.
passthrough-player-counts: false
# Enable LEGACY ping passthrough. There is no need to enable this unless your MOTD or player count does not appear properly.
# This option does nothing on standalone.
legacy-ping-passthrough: false
# How often to ping the remote server, in seconds. Only relevant for standalone or legacy ping passthrough.
# Increase if you are getting BrokenPipe errors.
ping-passthrough-interval: 3

# Maximum amount of players that can connect
max-players: 100

# If debug messages should be sent through console
debug-mode: false

# Thread pool size
general-thread-pool: 32

# Allow third party capes to be visible. Currently allowing:
# OptiFine capes, LabyMod capes, 5Zig capes and MinecraftCapes
allow-third-party-capes: true

# Allow third party deadmau5 ears to be visible. Currently allowing:
# MinecraftCapes
allow-third-party-ears: false

# The default locale if we dont have the one the client requested
default-locale: en_us

# Configures if chunk caching should be enabled or not. This keeps an individual
# record of each block the client loads in. While this feature does allow for a few
# things such as block break animations to show up in creative mode and among others,
# it is HIGHLY recommended you disable this on a production environment as it can eat
# up a lot of RAM. However, when using the Bukkit version of Geyser, support for features
# or implementations this allows is automatically enabled without the additional caching as
# Geyser has direct access to the server itself.
cache-chunks: false

# Bedrock prevents building and displaying blocks above Y127 in the Nether -
# enabling this config option works around that by changing the Nether dimension ID
# to the End ID. The main downside to this is that the sky will resemble that of
# the end sky in the nether, but ultimately it's the only way for this feature to work.
above-bedrock-nether-building: false

# bStats is a stat tracker that is entirely anonymous and tracks only basic information
# about Geyser, such as how many people are online, how many servers are using Geyser,
# what OS is being used, etc. You can learn more about bStats here: https://bstats.org/.
# https://bstats.org/plugin/server-implementation/GeyserMC
metrics:
  # If metrics should be enabled
  enabled: true
  # UUID of server, don't change!
  uuid: generateduuid

# DO NOT TOUCH!
config-version: 3
```