---
sidebar: auto
---

# OpenGM for Group Members

## Admins

Just type `/adminlist`, this will list all admins in that group.

## Away from Keyboard mode

You can mark yourself as afk, just by typing `/afk` or `brb`. As soon as you write any other message, you will
automatically get marked as available. While you are afk, people who mention you (@Karatek_HD) will get notified about
you beeing afk. You can even set a reason for you being afk by using `/afk <reason>`

## Abouts

You can set a small "about-you" text for your user. Use `/setme <text>` to set it and see how it looks with `/me`.

## Bios

You can set sombody elses bio with `/setbio <text>` and read it with `/bio <userhandle>`. You can't change your own bio,
you're at the mercy of others!

## Notes

Notes allow group admins to store frequently accessed messages so users can find them quickly.

### Getting a note

This is possible through two ways: Sending `#<notename>` or `/get <notename>`.

### Listin all notes

Just send `/notes` or `/saved`.

## Reporting

You can report a message to the admins by using `/report <reason>` or `@admin` as a reply to a message.

## Sed/Regex

Reply to a message with `s/<text1>/<text2>(/<flag>)` to perform a sed operation on that message, replacing all
occurrences of 'text1' with 'text2'. Flags are optional, and currently include 'i' for ignore case, 'g' for global, or
nothing. Delimiters include /, _, |, and :. Text grouping is supported. The resulting message cannot be larger than

4096.

If you don't know how sed works, refer to its [documentation](https://www.gnu.org/software/sed/manual/sed.html).

**Reminder:** Sed uses some special characters to make matching easier, such as these: +*.?\
If you want to use these characters, make sure you escape them!
eg: \?.

## Grammar

Reply to a message with `/t` and the bot will reply with a corrected version of that message.

## Reputation

The Reputation system gives you some sort of "score" in every group. Other users can vote on your messages and change
your reputation! Reply to somebody elses message with `+` or ":+1:" to increase their reputation and with `-` or ":-1:"
to decrease it!

You can opt yourself out of this system using the `/reputation` command in a private chat with the bot: `/reputation on`
enables it, `/reputation off` disables it.

## Filters

Some groups have filters that automatically reply to a message if it contains a certain keyword. You can list these
filters using `/filters`.

## Miscellaneous

### Listing disabled commands

Some commands might be disabled in some groups and cannot be executed in that group.
You can list disabled commands using `/cmds`.

### Getting IDs

`/id` will get the current group id. If used by replying to a message, gets that user's id.

### Checking whether the bot is up

The `/runs` command will print a random line. It works in groups and in private chats!

### Slapping

`/slap <userhandle>` will get you slapped.

### Userdetails

Run `/info <userhandle>` to get some information about a user! This usually looks somehow like this:
| Example |
| ----------------------------------------------------------- |
|  **User info:**                                                          |
| ID: 540549815 |
| First Name: Karatek_HD |
| Username: @Karatek_HD |
| Permanent user link: link |
| |
| This person is my owner - I would never do anything against them!|
| Globally banned: No |
| About user: |
| Student from Germany, Software developer. Owner of @karatekbot |
| |
| I've seen them in 13 chats in total. |

### Deleting all your information

Execute `/gdpr` in a private chat (!) to delete all your information from the bot's database.

### Markdown Help

Use `/markdownhelp` in a private chat for a quick summary of how markdown works in Telegram.