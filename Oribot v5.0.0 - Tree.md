#suggestions 

## What is Oribot?

A custom bot running on .NET 6 that is built from the ground up for the Ori the Game Discord, utilizing Discord.NET and NoSQL Database.


# Table of Contents
- [Features](#Project%20Scope%20|%20Features)
- [Infrastructure](#Bot%20Infrastructure)
- [Design Ideas](#Design%20Ideas%20|%20Mandatory%20Features)
- [Command Summary](#Potential%20(Slash)%20Commands)

## Project Scope | Features
- [Safety & Setup](Safety%20&%20Setup.md)
- [Moderation Features](Moderation%20Features.md)
- [Passive Bot Interactions](Passive%20Bot%20Interactions.md)
- [User Features](User%20Features.md)
- [...]

## Bot Infrastructure
- [Logging](Logging) #logging
- Command Handling #command-handling 
	- [Passive Command List](Passive%20Command%20List.md)
	- [Slash Commands](Slash%20Commands.md)
	- [Traditional Commands](Traditional%20Commands.md)
- [Storage](Storage) #storage 
- [Permission System](Permission%20System.md) #permission-access 
- [...]

## Design Ideas | Mandatory Features
**REVISION NEEDED**

#command-handling
- Must have a simple command structure. This means more commands, less subcommands. 
	- Break up command trees into more easily digested, smaller commands with fewer subcommands
	- Test moving to slash commands
#logging 
- Overhauled log system. Must be able to enter, view and delete entries.
	- Implement a feature for deleting log entries instead of simply hiding them
	- Must use JSON database for more reliable storage
	- Bot must DM the user any warns, mutes, bans etc.
#system
- Should migrate anti-spam, Steam API, and Gallery Pins since they’re API-independent.
#system 
- Improve maintainability of the bot
	- Implement encapsulation
	- Should be accessible for multiple servers.
- Reimplement the existing profile system with identical features in JSON.
#permission-access 
- Reimplement access controls. see [Permission Levels](Moderation%20Features#Permission%20Levels)
	- Simplify with a tighter scale, rather than 0 to 128 like now
		- New User
		- Validated User
		- Moderator
		- Bot Admin
#admin  
- Rework the ticket system
	- Allow use of ticket within the server for less confusion
#command-handling 
- Add Bot-Commands responses 
#misc #command-handling 
- Dice Rolls


- Must be compatible with existing data.
	- Alternatively, write conversion script to convert existing data to the new format.

### Libraries and Targets
- C#
- Discord.NET
- Ubuntu Server as Target Platform
- JSON NoSQL Database


## Potential (Slash) Commands

#mod-commands | More Info [Here](Moderation%20Features#Moderator%20Commands)
`>> mute [User ID] [Reason] [Duration]`
	Mutes a user for the given duration, logs the mute, and DMs them with [Reason]. Moderator only.

`>> unmute [User ID] [Reason]`
	Unmutes a user. Moderator only.

`>> warn [harsh, minor] [User ID] [Reason]`
	DMs the user with an automated warning, and logs it internally. Moderator only.

`>> warnlog [User ID] [Entry Index]`
	Allows for viewing a user's log, or view a specified entry. Moderator only.

`>> deletelog  [User ID] [Entry Index] [Reason]`
	Deletes the given log entry and logs a reason for deletion. Moderator only.

`>> note [User ID] [Note Content]`
	Logs a note about a potentially problematic user. Moderator only.

`>> ban [User ID] [Reason]`
	Bans the given user and DMs them with [Reason]. Moderator only.

`>> addbadge [User ID] [Badge Name]`
	Adds a badge to a user's profile. Moderator only.


#admin | More Info [Here](Moderation%20Features#Admin%20Commands)
`>> restart [reason]`  #suggestions **Added Suggestion by Slam - [reason]**
	Forces the bot to restart. Bot Admin Only. [reason] is optional.

`>> shutdown [reason]` #suggestions **Added Suggestion by Slam - [reason]**
	Shuts the bot down. Bot Admin Only. [reason] is optional.

#suggestions **by Slam**
`>> chw [channel-id]` (alias)
`>> channelWhitelist [channel-id]`
	Whitelists a channel for the bot to not monitor

#suggestions **by Slam**
`>> chs [Channel ID] [bot | logs | art]` (alias)
`>> channelSettings [Channel ID] [ bot | logs | art]`
	Sets a channel if it is either a bot-commands channel, a log channel, or an art-gallery channel.


#user-commands | More Info [Here](User%20Features)
`>> profile [User ID]`
	Brings up a user's profile, or your own if you don't include an ID.

`>> updatestatus [Status Text]`
	Updates the status entry of your profile. %%what's this%%

`>> updatebio [Bio Text]`
	Updates the bio entry of your profile.
%%can perhaps add a subcommand under profile? Same goes to others (just in case)%%

`>> color [Color Name | List]`
	Adds a color role to you, or lists available colors.

`>> hug`
	Ori gives you a hug! (unless… :flushed:)

`>> ticket`
	Opens a thread where moderators can address an issue.

`>> info`
	Displays all the bot's metadata, owner, contributors, version, and etc.

`>> help [command]`
	sends a list of commands/command usage