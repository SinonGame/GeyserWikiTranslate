Commonly, people may have issues with Geyser not showing up in their server list or run into similar issues. This page contains a few common issues people may encounter that you might have as well as potential fixes for them. If you still can't make it work, join [our Discord](https://discord.geysermc.org) for support.

# "Unable to connect to world"
This error means that the Bedrock client cannot find the server. If this occurred after updating a plugin version of Geyser, ensure that you shut off your server, swapped the Geyser jar, and then started up your server.

Otherwise, check the solutions below for potential solutions, make sure you're port forwarded or make sure your hosting provider can support Geyser.

## Pterodactyl
If you get this error while using the Pterodactyl Panel, try editing the Geyser config and changing the port to something besides `19132` (e.g. `25566`).

# Geyser Not Showing Up in Server List
This is a _very_ common occurence and is usually one of a few problems nearly every time.

## Loopback Restrictions Not Lifted

_This only affects people trying to join Geyser from Windows 10 Edition with Geyser hosted on the same computer._

This is an issue caused by Loopback restrictions not being lifted. By default, Microsoft Apps have this restriction on all their apps for local connections. You can lift it by typing the following in Windows PowerShell in administrator mode:
```powershell
CheckNetIsolation LoopbackExempt -a -n="Microsoft.MinecraftUWP_8wekyb3d8bbwe"
```

In most cases, Geyser should resolve this issue automatically, but in some events where you may not be an administrator, this will not automatically be resolved.

## Geyser Not Showing Up in Friends Tab
This is also a common one, Geyser won't always show up in your friends tab and you will have to manually add it through the servers tab. Start off by just using `localhost` or `0.0.0.0` as the IP address. If that does not work, use your **local** IPv4 address.

## Geyser Showing Up On Local Computer But Not Anywhere Else

Check your firewall settings and make sure that Java is allowed.

## SRV Records Not Properly Working

Bedrock edition does not support SRV records, so this option won't work at all.

## Using TCP in DNS Options or Portforwarding Instead of UDP

Bedrock uses UDP instead of TCP, so you will have to update your DNS or port forward accordingly if you are using TCP instead.

## Server on External Host Can't Be Connected to Despite Java Players Being able to Connect
This usually has something to do on your host's end. Most commonly, it's because they do not open up ports over the UDP protocol, which is what Minecraft: Bedrock Edition uses, opposed to Minecraft: Java Edition using TCP. One way to get around this (if you're using an online host) is to shut down your server, and when asking for a server jar, select Nukkit (you won't actually be switching to Nukkit). Afterward, open up your FTP file manager and find the Nukkit jar. Then, replace this jar with the server software you're using. Upon starting up the server, it should open up ports over UDP whilst still allowing you to use the server jar you desire.

**PLEASE NOTE:** If your server automatically redownloads jars upon startup, such as with an autoupdate system, this workaround will not work. Please contact your host if this does not work for you as there is nothing we can do.

# java.net.BindException: Address already in use: bind
This means something (likely another instance of Geyser) is running on the port you have specified in the config. Please make sure you close all applications running on this port. This is sometimes due to the fact that you doubleclicked the jar instead of running it using a startup script. If you don't recall opening anything, usually restarting your computer fixes this. 

# Login Failed

## Server is in Online Mode while Geyser is in Offline Mode (Access token can not be null or empty)
If you have your configuration set up like this, put simply, it won't work. If authentication for the Java server is set to online, it is expected Geyser is configured the same way. The server requires a valid Minecraft: Java Edition account, and if you aren't logging into one with Geyser, then you will be unable to join the server. If your configuration is set up properly and you're still getting this issue, it could be that your credentials are invalid.

## Floodgate Misconfiguration
See [this page](Floodgate) for more information.

## Mojang Resetting Account Credentials
This is unfortunately something we have no control over, and is most likely the case when you're running Geyser as a plugin on a server host or joining a friend far away from your location. If you're running Geyser locally, this should not happen to you, but what we recommend for servers is a plugin we make called [Floodgate](https://github.com/GeyserMC/Floodgate), which allows for Bedrock clients to join your server without needing a Java Edition account. Take a look [here](Floodgate) for more information. 

# java.lang.AssertionError: Expected AES to be available

Update your Java at [AdoptOpenJDK.net](https://adoptopenjdk.net/).

# Geyser Bukkit plugin does not load with CraftBukkit/other error with CraftBukkit

Geyser is not tested with CraftBukkit, and Floodgate will not load with CraftBukkit. We recommend you use the Paper or Spigot server software.

# Bedrock clients freeze when opening up commands for the first time
Disable `command-suggestions` in your Geyser config. This will stop the freezing at the expense of removing command suggestions from Bedrock clients.

# BungeeCord freezes and crashes after bedrock player joins
Make sure you have set `ip-forward` to `true` in your BungeeCord `config.yml` and set `bungeecord` to `true` in each connected server's `spigot.yml`.

# Floodgate
For most floodgate issues see: [Floodgate: Known Issues/Caveats](Floodgate#known-issuescaveats).
## If you wish to use IP forwarding, please enable it in your BungeeCord config as well!
It is likely you have enabled `send-floodgate-data` in your Floodgate config but either Floodgate isn't installed on the target server or you floodgate keys aren't the same between the installs of the plugin, please copy them so they all use the same set.