PowerShell IRC Bots
===================

`Make-Alive.ps1` is an easy way to make IRC bots using PowerShell.

```PowerShell
.\Make-Alive.ps1 [-Name] <string> [-Server] <string> [-Channels] <string[]> [[-BotScript] <Object>] [-State <Object>] [-Silent] [<CommonParameters>]
```

Simple usage:
```PowerShell
.\Make-Alive.ps1 awesomebot ircserver chan1,chan2,chan3
```
...where .\awesomebot.ps1 is the script containing the bot.

Position | Option | Value
--- | --- | ---
1 | `[-Name] *name*` | **Required.** The user and nickname of your bot. If a `-BotScript` is not provided, then this is also the name of the script. If you pass a file, the user and nickname used is the basename of the file (no path, no extension).
2 | `[-Server] *server[:port]*` | **Required.** The server to connect to with optional port. The default port is 6667.
3 | `[-Channel] *chan1,chan2,...*` | **Required.** A comma-delimited list of channels your bot will join on startup, without leading `#`.
4 | `[-BotScript] *script*` | An invokable script that represents your bot. This can be the name of the script or a script block. By default, the `-Name` is used.
* | `-State *object*` | Initial state to pass into `$Bot.State`. Default state is an empty hash: `@{}`
* | `-Silent` | Suppresses default host output.
* | `-Verbose` | Enables verbose output for the IRC bot.

