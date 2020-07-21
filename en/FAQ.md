## How Does it Work?
Geyser works as a translator, translating both the incoming and outgoing packets to a format both the client and server can understand. With this being said, it emulates a Minecraft: Java Edition client, so the server actually thinks you're joining from Java Edition. Regardless of the server or what plugins it has installed, you can join it with Geyser (as long as the server supports the latest Minecraft version).

## What plugins don't work with Geyser?
* [JPremium](https://www.spigotmc.org/resources/%E2%96%A0-jpremium-%E2%96%A0-advanced-authorization-system-with-auto-login-the-premium-players-%E2%96%A0-1-8-1-15-2-%E2%96%A0.27766/) alters the UUID of a player causing Floodgate to not be able to get the Bedrock data from its map.
* [ProtocolSupport](https://www.spigotmc.org/resources/protocolsupport.7201/) sometimes causes issues with Floodgate saying `Invalid packet id: 27`. Use [ViaVersion](https://www.spigotmc.org/resources/viaversion.19254/) instead if this keeps occurring.
* [TCPShield](https://tcpshield.com/) causes Floodgate not to be able to authenticate.

If you come across any more please let us know via [Discord](http://discord.geysermc.org).

## Which plugin version of Geyser do I need?
This is a non-complete list of what platform each plugin version of Geyser is for, the standalone version can be used for any as it isn't a plugin.
* Geyser-Spigot works with:
  * [Spigot](https://www.spigotmc.org/)
  * [Paper](https://papermc.io/downloads) (recommended)
  * Any other forks of the above
* Geyser-Bungee works with:
  * [BungeeCord](https://www.spigotmc.org/wiki/bungeecord/)
  * [Waterfall](https://papermc.io/downloads#Waterfall)
  * Any other forks of the above
* Geyser-Velocity works with [Velocity](https://www.velocitypowered.com/) *1.1.0 or later*
* Geyser-Sponge works with [SpongeVanilla or SpongeForge](https://www.spongepowered.org/)

## If using BungeeCord or another fork, where do I need to put Geyser/Floodgate?
You only need Geyser and/or Floodgate on the BungeeCord server.

## How do I add players to the whitelist when using Floodgate?
There are two ways you can do this. The first way is to turn off the whitelist using `/whitelist off`, then get the Geyser player to join, then run `/whitelist add "username"`, then turn the whitelist back on using `/whitelist on`. The second way is to add the player's UUID as given by Floodgate to the whitelist.json file and then run `/whitelist reload`.

## How do I find a player's UUID without them joining when using Floodgate?
Use [this page.](https://floodgate-uuid.heathmitchell1.repl.co/) If this doesn't work then try this method:
<br><br>
First, you'll need to get the XUID of the player. There are several third-party websites to find this, for example [this one](https://cxkes.me/xbox/xuid) (unaffiliated with Geyser). Make sure to choose "
Hexidecimal". You'll need to enter the player's Xbox gamertag, and once submitted it should display the XUID in the format of `xxxxxxxxxxxxxxxx`. In order to turn the XUID into a UUID that Java Edition can recognize, you just need to put the XUID in this format: `00000000-0000-0000-xxxx-xxxxxxxxxxxx`. If formatted right, Java Edition should accept it as a UUID.

## Can I use Geyser with Pterodactyl Panel?
Yes, we have an official egg for the standalone version, it supports auto-updating and has all config options easily editable. You can find it [here](https://github.com/GeyserMC/pterodactyl-stuff), just download the JSON egg and import it into your panel.

## Can I use Geyser with Ngrok?
Unfortunately Ngrok is TCP-only, so you will not be able to use Geyser with Ngrok.

## Can I use Buycraft with Geyser?
You sure can! Buycraft supports Java & Bedrock players via the Offline store mode **(Recommended to be used with Floodgate)**
### Steps to create a store to support both versions
- Buycraft-> Create Webstore
- Select Game-> Minecraft Offline
- Continue-> Click "Create my Webstore"
- Name your server & Select currency-> Continue
- Select Game Server-> Continue
- Download the plugin version that best suits your server.
- Execute the secret command from your servers console

Your store is now setup to support Bedrock & Java players

**(PLEASE NOTE, BEDROCK PLAYERS MUST INCLUDE THE PREFIX)**

## What languages does Geyser support?
We aim to support any of the bedrock languages, see [here](https://translate.geysermc.org/) for our Crowdin page and below is a list of all the language codes.
|Name                        |Code |
|----------------------------|-----|
|Bulgarian                   |bg_bg|
|Czech                       |cs_cz|
|Danish                      |da_dk|
|German                      |de_de|
|Greek                       |el_gr|
|British English             |en_gb|
|American English            |en_us|
|Spanish                     |es_es|
|Mexican Spanish             |es_mx|
|Finnish                     |fi_fi|
|Canadian French             |fr_ca|
|French                      |fr_fr|
|Hungarian                   |hu_hu|
|Indonesian                  |id_id|
|Italian                     |it_it|
|Japanese                    |ja_jp|
|Korean                      |ko_kr|
|Dutch                       |nl_nl|
|Norwegian Bokmål            |nb_no|
|Polish                      |pl_pl|
|Brazilian Portuguese        |pt_br|
|Portuguese                  |pt_pt|
|Russian                     |ru_ru|
|Slovak                      |sk_sk|
|Swedish                     |sv_se|
|Turkish                     |tr_tr|
|Ukrainian                   |uk_ua|
|Chinese Simplified (China)  |zh_cn|
|Chinese Traditional (Taiwan)|zh_tw|
