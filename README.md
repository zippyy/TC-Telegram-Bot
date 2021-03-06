# TC-Telegram-Bot
This is a Telegram bot that execute commands in [TrinityCore](https://community.trinitycore.org/topic/14582-trinitycore-and-telegram-integration/?tab=comments#comment-85953) or [AzerothCore](http://www.azerothcore.org/) console via telnet.


If you don't know how to set up a basic Telegram Bot, read this first:  [https://core.telegram.org/bots](https://core.telegram.org/bots) and talk with [@BotFather](https://t.me/BotFather)


## Installing

To run this bot you need the python-telegram-bot library, you can install it by

`pip install python-telegram-bot`

To install it from source you can download it from [https://github.com/leandrotoledo/python-telegram-bot](https://github.com/leandrotoledo/python-telegram-bot)




## Configuration

After installing the client you must configure it settings the following parameters:

```
HOST = "127.0.0.1"	#IP of the server
port = 3443		#Port of the server
username = ""		#Username telnet access 
password = ""		#Password telnet access
logs = 1			#Enable/Disable logs (1/0)

TOKEN = ""		#Token of your telegram bot that you created from @BotFather
```

The last parameter it's the Token of your bot that you receive while creating it with [@BotFather](https://t.me/BotFather) (ask this bot on telegram).

After configuration you can run your bot, remind to enable telnet in etc/worldserver.conf (RA.* settings) and open your worldserver.

## Security

You can add a condition filter to this line that active the bot only with your chat throught the chat_id:

https://github.com/Helias/TC-Telegram-Bot/blob/master/telegrambot.py#L72

just adding "and chat_id == your_chat_id".

What is chat_id? Anyone on Telegram has a chat_id which any bot use to recognize you and send a message.

How can I find my chat_id? You can obtain your chat id just sending /chatid to [@GiveChatId_Bot](https://t.me/GiveChatId_Bot).

(if you want to obtain the chatid of a group you must invite [@GiveChatId_Bot](https://t.me/GiveChatId_Bot) to the group and write /chatid, the chat_id of the gorup usually are negative).

## Usages

Here the commands that are actually supported:

```
/saveall 
/serverinfo - show server info
/ticket list - show ticket list
/ticket onlinelist - show ticket onlinelist
/ticket viewid {ID}
/ticket complete {ID} {Reason}
/mute {PlayerName} {minutes} {reason}
/mutehistory {accountName}
/unmute {PlayerName}
/gmannounce {testo}
/announce {testo}
/tele {PlayerName} {Area}
/reload {table}
/revive {PlayerName}
/pinfo {PlayerName}
/kick {PlayerName}
/unstuck {PlayerName}
/baninfo ip/account/character {ip/accountName/playerName}
```

## Examples:

![Example1](https://raw.githubusercontent.com/Helias/TC-Telegram-Bot/master/Example1.png)

![Example2](https://raw.githubusercontent.com/Helias/TC-Telegram-Bot/master/Example2.png)
 


## FAQ

(the follow error should be fixed from this commit https://github.com/Helias/TC-Telegram-Bot/commit/023cc54b262afd644f1ac362c91e9c88f0a9dced )

My bot **doesn't run** and **return the follow error**:

```
    LAST_UPDATE_ID = bot.getUpdates()[-1].update_id
IndexError: list index out of range
```

Send a message to your Bot and (re)run the file telegrambot.py.


### Contribute

You can help me [opening a new issue](https://github.com/Helias/TC-Telegram-Bot/issues/new) to report a bug or a suggestion

or you can donate to support me

[![Donate](https://www.paypal.com/en_GB/i/btn/btn_donateCC_LG.gif "Donate")](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=52AZFFD86N39Q)
