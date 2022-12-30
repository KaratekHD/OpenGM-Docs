---
sidebar: auto
---

# OpenGM for Group Admins

## Administrator management

### Promoting users

Use `/promote <userhandle>` or `/promote` as a reply to a message from the person you want to promote, and it will
become a chat admin.

### Demoting users

Use `/demote <userhandle>` or `/demote` as a reply to a message from the person you want to demote, and it will lose
its admin privileges.

## Antiflood

These settings allow you to fight against spammers, by banning people who are sending to many messages in a short period
of time.

You can view the current settings using the `/flood` command. To change them, use `/setflood <int>` to set the flood
limit or `/setflood 'off'` to disable antiflood completly.

## Bans

Users can be banned permanently using the `/ban <userhandle>` command or temprary using
the `/tban <userhandle> x(m/h/d)` command (where userhandle is a mention or the message is sent as a reply. `x` can be
every number, and m / h / d is the time unit).

You can use `/unban <userhandle>` to unban a user.

## Kicks

If you feel like banning a user is a bit harsh, you can use `/kick <userhandle>` to kick them from you group. They will
still be able to rejoin later.

## Mutes

Users can be muted using the `/mute <userhandle>` command. You can also use `/tmute <userhandle> x(m/h/d)` (where
userhandle is a mention or the message is sent as a reply. `x` can be
every number, and m / h / d is the time unit) to mute a user only for a certain time.

User can be unbanned using the `/unmute <userhandle>` command.

## Word Blocklists

Blacklists are used to stop certain triggers from being said in a group. Any time the trigger is mentioned, the message
will immediately be deleted. A good combo is sometimes to pair this up with warn filters!

**NOTE**: blacklists do not affect group admins.

### See current blacklist

The `/blacklist` command lists the current blacklisted words.

### Add a trigger to the blacklist

The `/addblacklist <triggers>` command allows you to add words to the blacklist. Each line is considered one trigger, so
using different lines will allow you to add multiple triggers.

### Remove triggers from the blacklist.

The commands `/unblacklist <triggers>` and `/rmblacklist <triggers>` remove words from the blacklist. The same newline
logic applies here, so you can remove multiple triggers at once.

## Command disabling

In larger groups, you might want to disable certain commands for group members.

This can be achived with the `/disable <command>` command. You can also reenable commands using `/enable <command>`.
The `/listcmds` command returns a list of toggelable commands.

## RSS Feeds

You can subscribe your group to as many RSS feeds as you want. New entrys in the feed will be posted to your group.

To add a feed to your group, do the following:

1. Use `/rss <link>` to validate that the feed link is valid.
2. Add the feed by typing `/addrss <link>`.
3. Verify that the feed has been added to your group using `/listrss`.
4. You can remove a feed using `/removerss <link>`.

## Filters

Filters allow the bot to react to messages with a certain keyword.

Using `/filter <keyword>` will add a filter to this chat. The bot will now reply that message whenever 'keyword'is
mentioned. If you reply to a sticker with a keyword, the bot will reply with that sticker. NOTE: all filter keywords are
in lowercase. If you want your keyword to be a sentence, use quotes. eg: `/filter "hey there" How you doin?`

Filters can be stopped by using `/stop <keyword>`.

## Global Bans

Gbans, also known as global bans, are used by the bot owners to ban spammers across all groups. This helps protect you
and your groups by removing spam flooders as quickly as possible.

Running `/gbanstat <on/off/yes/no>` will disable the effect of global bans on your group, or return your current
settings when called without arguments.

## Locks

In larger groups, you might want to limit what types of messages users can send.

Possible locktypes are:

- sticker
- audio
- voice
- document
- video
- videonote
- contact
- photo
- gif
- url
- bots
- forward
- game
- location
- messages
- media
- other
- all

You can print this list by running `/locktypes`.

Using `/lock <type>` or `/unlock <type>` with one type from the list of locktypes locks/unlocks it.

`/locks` returns a list of the current locks in the chat.

## Notes

Notes allow you to store frequently accessed messages so users can find them quickly.

`/save <notename> <notedata>` saves notedata as a note with the name notename.
A button can be added to a note by using standard markdown link syntax - the link should just be prepended with a
buttonurl: section, as such: `[somelink](buttonurl:example.com)`. Check `/markdownhelp` for more info.

You can delete a note using `/clear <notename>`.

## Pins