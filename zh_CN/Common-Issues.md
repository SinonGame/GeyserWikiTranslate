通常情况下，人门经常会有Geyser服务器不显示或者类似的问题。此页面包含了一些常见的问题和可能的修复办法，如果你还是无法修复问题，请加入[官方Discord](https://discord.geysermc.org)寻求帮助。

# "无法连接至世界"
此错误表示Bedrock客户端无法连接到服务器。如果这个问题在升级了插件版Geyser后出现，确保你先关闭服务器，更换jar文件，然后启动服务器。

如果问题依然存在，请检查下面的内容以寻找解决方案，确保您已进行端口转发，并确保您的托管服务提供商可以支持Geyser。

## 翼龙面板
If you get this error while using the Pterodactyl Panel, try editing the Geyser config and changing the port to something besides `19132` (e.g. `25566`).
如果你在使用翼龙面板的时候出现了该错误，尝试修改Geyser配置，将端口更改为`19132`以外的端口 (例如 `25566`)

# Geyser不在服务器列表中出现
这是一个 _很_ 常见的问题，是基本上每次都要解答的一个问题。

## 环回限制未解除

_这个问题只影响那些在自己电脑上托管Geyser的Windows 10版本玩家_

这个问题是因为环回限制未解除导致的。默认情况下，Microsoft Store中下载的App对于本地连接都有环回限制。你可以通过在管理员模式下的PowerShell中输入以下代码来解除限制:
```powershell
CheckNetIsolation LoopbackExempt -a -n="Microsoft.MinecraftUWP_8wekyb3d8bbwe"
```

通常情况下，Geyser会自动解决此问题，但是如果您不是以管理员身份运行的Geyser，此问题不会被自动解决。

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