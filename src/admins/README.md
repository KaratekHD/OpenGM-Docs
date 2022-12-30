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

Replying to a message with the `/pin` command will pin it to the chat. `/unpin` unpinns all pinned messages.

## Message Deletion

Sometimes, you have to delete a lot (and I mean a lot) of message at once. That's where <code>/purge</code> comes in.

Replying to a message with `/purge` will delete **all** messages which have been sent after this certain message.
If you provide an additional integer (`/purge <x>`), it will delete `x` messages.

**NOTE**: The bot can't delete messages sent by other bot accounts due to limitations in the Telegram API.

## Warnings

Warnings allow you, as an admin, to warn users if they missbehave. After a certain amount of warnings (defaults to 3)
they will get banned from the group.

### Basics

The `/warns <userhandle>` command lists a user's warns. Warnings can be resetete using `/resetwarn <userhandle>`.

The warning limit can be changed using the `/warnlimit <int>` command.

Using `/strongwarn <on/yes/off/no>` it is possible to kick users when they exceed the warning limit (instead of banning
them). Defaults to on.

### Manual Warns

`/warn <userhandle>` warns a user. It can be removed by clicking the inline button below the confirmation message the
bot sends.

### Automatic Warns

Manually warning users can be a real hazzle. With warning filters the bot can do this automatically for you!

`/addwarn <keyword> <reply message>` sets a warning filter on a certain keyword. If you want your keyword to be a
sentence, encompass it with quotes, as such: `/addwarn "very angry" This is an angry user. `

`/nowarn <keyword>` stops a warning filter.

## Welcome/Goodbye messages

**NOTE**: The commands in this section work identically for welcome-messages and goodbye-messages, so e.g. `/setwelcome`
works for welcome-messages and `/setgoodbye` for goodbye-messages.

Your group's welcome/goodbye messages can be personalised in multiple ways. If you want the messages to be individually
generated, like the default welcome message is, you can use these variables:

- _{first}_: this represents the user's first name
- _{last}_: this represents the user's last name. Defaults to first name if user has no last name.
- _{fullname}_: this represents the user's full name. Defaults to first name if user has no last name.
- _{username}_: this represents the user's username. Defaults to a mention of the user's first name if has no username.
- _{mention}_: this simply mentions a user - tagging them with their first name.
- _{id}_: this represents the user's id
- _{count}_: this represents the user's member number.
- _{chatname}_: this represents the current chat name.

Each variable MUST be surrounded by _{}_ to be replaced.
Welcome messages also support markdown, so you can make any elements bold/italic/code/links. Buttons are also supported,
so you can make your welcomes look awesome with some nice intro buttons.
To create a button linking to your rules, use this: `[Rules](buttonurl://t.me/karatekbot?start=group_id)`. Simply
replace `group_id` with your group's id, which can be obtained via `/id`, and you're good to go. Note that group ids are
usually preceded by a - sign; this is required, so please don't remove it.
If you're feeling fun, you can even set images/gifs/videos/voice messages as the welcome message by replying to the
desired media, and calling `/setwelcome`. If you need more help, see `/welcomehelp`.

You can toggle welcome messages by using `/welcome <on/off>`. Running `/welcome` without arguments will print the
current welcome settings. Executing `/welcome noformat`  shows the current welcome settings, without the formatting -
useful to recycle your welcome messages!

Using `/resetwelcome` and `/resetgoodbye` resets to the default messages.

If a lot of members join your group, all the welcome message can spam your group quite quickly.
Using `/cleanwelcome <on/off>` it is possible to make the bot "clean up" old welcome messages.
When enabled, the bot will try to delete the last welcome message once a new member joins.

## Reports

Users are able to report messages to the admins. Once a message is reported, the bot will send a PM to all the group
admins.
If you don't wan't to get all the reports to your inbox, use the `/reports <on/off>` in a private chat with the bot to
opt out of / into this feature. Using `/reports` without any arguments returns the current setting.

## Invitelink

The `/invitelink` command returns the groups invite link.

