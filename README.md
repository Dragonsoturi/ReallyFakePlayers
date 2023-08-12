<picture><source media="(prefers-color-scheme: dark)" srcset="https://github.com/marlester-dev/ReallyFakePlayers/assets/77095872/0e39fec6-495a-4d9b-acab-2db092f5b9f5"><source media="(prefers-color-scheme: light)" srcset="https://github.com/marlester-dev/ReallyFakePlayers/assets/77095872/0e39fec6-495a-4d9b-acab-2db092f5b9f5"><img src="https://github.com/marlester-dev/ReallyFakePlayers/assets/77095872/0e39fec6-495a-4d9b-acab-2db092f5b9f5" alt="Logo"><picture><br />
# PLUGIN IS UNDER REWRITE, NO PULL REQUESTS OR SIMILAR, PLEASE WAIT A MONTH OR SO.
# ReallyFakePlayers (Updated)
Simulates fake players on a server, tricks server lists and boosts your online.<br />
A fork and updated version of ReallyFakePlayers for 1.19.4 - 1.20.<br />

Works on Spigot (and should work on it's forks).<br />
Plugin is still beta, expect bugs, report them in issues tab.<br />

## Downloads
Download plugin: https://dev.bukkit.org/projects/really-fake-players/files

(for 1.17.1 and 1.18.2, not my and not supported):

1.17.1 (freethemice): https://spigotmc.org/resources/really-fake-players.95927

1.18.2 (tristiisch): https://github.com/tristiisch/ReallyFakePlayers/releases
##
This a fork of freethemice's ReallyFakePlayers (TitanBoxRFP) plugin.<br />
Big thanks and credits to freethemice (github.com/freethemice).<br />
freethemice gave me permission to modify & redistribute this plugin.
Thanks to tristiisch as well, because I took some sources from him. (he game me permission)

## Installation guide
1. Stop server
2. Drop plugin in plugins folder
3. Start server
4. Wait for server to fully load
5. Stop server
6. Modify config.yml in plugins/ReallyFakePlayers/config.yml
7. Start server if you wish
8. Done

## Optional dependencies
Vault plugin and permissions plugin are needed to make bots have groups/ranks.<br />
Vault integration will not work if no permissions plugins are present.<br />
Any other permissions plugins except PEX and LuckPerms are not supported.<br />
You may disable Vault integration by changing respect-vault: true to respect-vault: false in config file.<br />
**NEW**: PlaceholderAPI integration! RFP adds 2 new placeholders to PAPI: %rfp_online_with_fakeplayers%<br />
and %rfp_online_without_fakeplayers%. You can also use placeholders from PAPI in config messages.<br />
You may disable PAPI integration by changing respect-papi: true to respect-papi: false in config file.<br />

## Information
1. Would not recommend adding more than 60 players, but you can.
2. Because the server thinks players are really a command blocker will stop commands with fake players name. (can be turned off in settings under interaction)
3. If a really player logs in with the same name as a fake player, the fake player will be removed.
4. NameList.yml hold all the random names
5. [I'm Fake] and [Fake Player] can only be seen by ops.
6. Fake players do not have bodies.
7. All fake players have "10.10.10.10" ip address
8. "MIT*" license with conditions

### Bug reports & MC Versions supported
Report bugs on the [issues tracker](https://github.com/marlester-dev/ReallyFakePlayers/issues)!
* ![Status-Fully supported-green](https://github.com/marlester-dev/ReallyFakePlayers/assets/77095872/2a64f571-007b-4fa2-ad00-e24755a81dd3)
* ![Status-Fully supported-green](https://github.com/marlester-dev/ReallyFakePlayers/assets/77095872/6653a216-6200-4644-81da-bdffde17f955)
* ![Bugfixes Only-orange](https://github.com/marlester-dev/ReallyFakePlayers/assets/77095872/a22ed804-15a2-42a7-8679-52ad58baff97)

## Contributing
Clone the repository via [Git](https://git-scm.com/downloads) using `git clone https://github.com/marlester-dev/ReallyFakePlayers`,<br />
Download and install official spigot [BuildTools](https://www.spigotmc.org/wiki/buildtools/) for needed mc version,<br />
Building requires JDK 17, run `./gradlew build` to compile the plugin (powershell/linux/macos),<br />
Jar will appear in the build directory, after making changes and testing, you can create a pull request.<br />

## Known bugs (maybe outdated)
If you get this error: java.lang: Asynchronous Chunk getEntities call,<br />
try disabling/enabling paper-performance-boost in config.<br />
Some plugins may throw errors in the console because of fake players network issues,<br />
(I minimized them, almost 90% of plugins are compatible now)<br />
be sure to submit a bug report and you may use ConsoleSpamfix plugin temporarily,<br />
There is a known error with NoCheatPlusUpdated, you should disable<br />
data consistencychecks in NCP config, or just supress warnings.<br />
Also, there is a strange error on /list command when Vault, LuckPerms<br />
and EssentialsX are installed and respect-vault is false, LP'll tell you about<br />
vault-unsafe-lookups, you should enable it in LP config to fix it, it is very<br />
specific problem and it's likely EssentialsX or LuckPerms are causing it.<br />

## Commands
```yaml
/rfp help - help command
/rfp add <#> - add X fakeplayers
/rfp add <name> - add fakeplayer
/rfp checkvaultavailability - check vault status
/rfp remove <name> - remove fakeplayer
/rfp remove all - remove all fakeplayers
/rfp list - list of them
/rfp reload - reload plugin (creeper bonus)
/rfp utfall - update tab-format
/rfp udnfall - update displayname format
```

## Permissions
```yaml
all commands: titanbox.admin or titanbox.rfp.admin
fake message: titanbox.rfp.show
```

## Default config.yml & explanation
*Maybe outdated.*
```yaml
#ReallyFakePlayer's plugin config file
#(also supports PlaceholderAPI) General internal placeholders: {fakeplayernick}, {fakeplayerdisplayname}, {fakeplayeruuid}

settings:
  maximum: 60 #The most maximum of fakeplayers that can be on the server (limiter).
  block_interaction: true #Blocks commands with fakeplayers (for players).
  block_interaction_to_ops: true #Blocks commands with fakeplayers (for admins).
  message: This player is on DND (Do Not Disturb)! #Message that should be written when block interaction.
  ops_fake_tag: true #Add [Fake Player] label for admins or no?
  respect-vault: true #If true, enable groups and permissions. (Requires Vault & PEX/luckperms)
  respect-papi: true #If true, enable PlaceholderAPI integration. (Requires PlaceholderAPI)
  show-in-tab: true #If false, fake players will not show up in tab. (also disables tab-completion)
  tab-format: 'default' #What name should fakeplayer have in tab? Set to 'default' if default.
  displayname-format: 'default' #What displayname should fakeplayer have? Set to 'default' if default.
  join-text: '&e{fakeplayernick} joined the game.' #Join text. (text that shows up when fakeplayer joins)
  vanilla-join-text: false #Will ignore option higher and use vanilla (multiplayer.player.joined) message.
  use-displayname-in-vanilla-join-text: false #If true, use displayname in vanilla join text.
  dont-send-join-text-to-players: false #If true, disables join text for players.
  dont-send-join-text-to-ops: false #If true, disables join text for admins.
  quit-text: '&e{fakeplayernick} left the game.' #The same as for join, but for quit.
  vanilla-quit-text: false #The same as for join, but for quit.
  use-displayname-in-vanilla-quit-text: false #The same as for join, but for quit.
  dont-send-quit-text-to-players: false #The same as for join, but for quit.
  dont-send-quit-text-to-ops: false #The same as for join, but for quit.
  invisibility-effect: true #If true, fakeplayers will have no-particles invisibility effect.
  anti-kick: true #Prevents anything from kicking fakeplayers.
  groups: #(Vault Integration) Groups, that fake players will have. (randomly chooses)
  - default
  fakeplayer-specific-permissions: [] #(Vault Integration) Permissions, that fake players will have.
  cleanup-groups-on-stop-and-quit: true #(Vault Integration) Will clean permission data of fakeplayer on leave.
  ping: #Ping fakeplayers will have (randomly chooses), updates on interval.
    min: 20
    max: 90 #Warning: MaxPing should be greater than MinPing.
  on-fakeplayer-join:
    run-commands-as-console: [] #Commands that will run as console after fake player joins.
  auto:
    enable: true #Enable/disable automatic fakeplayers addition.
    join_messages: true #If you disable this, fakeplayers will shut up.
    messageFormat: 'default' #Example: "{fakeplayernick}: <message>". <message> - placeholder.
    firstJoinMessages: #random messages they will say to first joining
    - "Welcome!"
    - "Welcome <name>!"
    - "Whats up <name>!"
    - "<name>!"
    - "Finally the one and only <name>!"
    reJoinMessages: #random messages they will say to rejoining players.
    - "WB"
    - "Welcome back <name>!"
    - "Hey, <name>!"
    - "Whats up <name>!"
    - "<name>!"
    - "Hello <name>!"
    - "WB <name>!"
    minimum: 3 #minimum amount of bots to create automatically
    maximum: 7 #maximum amount of bots to create automatically
    logging:
      seconds_interval_run: 30 #delay for running autologging (checks, removals, adds, pingsets).
      seconds_delay_join: 3 #number of seconds after startup before it will log all the fake players in.
      minimum_minutes: 5 #minimum time fake player can stay on server, after it expires, fakeplayer may leave with chancetoadd.
      maximum_minutes: 60 #(optimalstaytime disables this) maximum time fake player can stay on server, after it expires, fakeplayer leave.
      optimalstaytime: true #if true, make stay time optimal (disable maximum_minutes)
      chancetoadd: 15 #Chance to add fakeplayers if in-between minimum and maximum.
      chancetoremove: 15 #Chance to remove fakeplayer after his minimum_minutes expire.
      join: true #auto join.
      quit: true #auto quit.
  update-check:
    opt-out: false #self-explanatory.
    notify-players: true #notify admins?
  # ↓ Don't enable this if you are running official spigot or core that does not support asynchronous chunk getEntities call!
  # ↓ 3 options - 'default' - detects, 'enabled' - force enable, 'disabled' - force disable
  paper-performance-boost: 'default'

# ↓ These settings are unsupported!
unsupported-settings:
  ignoreluckpermscriticalbug: false #(Vault Integration) Basically allows you to run server with LuckPerms v5.4.88 or lower, but it has critical bug.
```
