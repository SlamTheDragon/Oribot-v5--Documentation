#outline #suggestions 

## What is Oribot?

A custom bot running on .NET 6 that is built from the ground up for the Ori the Game Discord, utilizing Discord.NET and NoSQL Database.


## Project Scope  
- [Moderation Features](Moderation%20Features.md)
- [User Customization](User%20Customization.md)
- [Passive Bot Interactions](Passive%20Bot%20Interactions.md)
- [...]

## Bot Infrastructure
- [Logging](Logging) #logging
- Command Handling #command-handling 
	- [Passive Commands](Passive%20Commands.md)
	- [Slash Commands](Slash%20Commands.md)
	- [Traditional Commands](Traditional%20Commands.md)
- [Storage](Storage) #storage 
- [Permission Access](Permission%20Access.md) #permission-access 
- ...

## Mandatory Features
**REVISION NEEDED**

- Must have a simple command structure. This means more commands, less subcommands.
	- Break up command trees into more easily digested, smaller commands with fewer subcommands
	- Test moving to slash commands
- Overhauled log system. Must be able to enter, view and delete entries.
	- Implement a feature for deleting log entries instead of simply hiding them
	- Must use JSON database for more reliable storage
	- Bot must DM the user any warns, mutes, bans etc.
- Should migrate anti-spam, Steam API, and Gallery Pins since they’re API-independent.
- Improve maintainability of the bot
	- Implement encapsulation
	- Should be accessible for multiple servers.
- Must be compatible with existing data.
	- Alternatively, write conversion script to convert existing data to the new format.
- Reimplement the existing profile system with identical features in JSON.
- Reimplement access controls #permission-access 
	- Simplify with a tighter scale, rather than 0 to 128 like now
		- New User
		- Validated User
		- Moderator
		- Bot Admin
- Rework the ticket system
	- Allow use of ticket within the server for less confusion
- Add Bot-Commands responses

#misc
### Optional features
- Dice Rolls

### Libraries and Targets
- C#
- Discord.NET
- Ubuntu Server as Target Platform
- JSON NoSQL Database


## Potential (Slash) #Commands

#mod-commands 
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

#user-commands
`>> profile [User ID]`
	Brings up a user's profile, or your own if you don't include an ID.

`>> updatestatus [Status Text]`
	Updates the status entry of your profile.

`>> updatebio [Bio Text]`
	Updates the bio entry of your profile.
%%can perhaps add a subcommand under profile? Same goes to others (just in case)%%

#mod-commands 
`>> addbadge [User ID] [Badge Name]`
	Adds a badge to a user's profile. Moderator only.

#user-commands 
`>> color [Color Name | List]`
	Adds a color role to you, or lists available colors.

`>> hug`
	Ori gives you a hug! (unless… :flushed:)

#admin #suggestions **Added Suggestion by Slam - [reason]**
`>> restart [reason]
	Forces the bot to restart. Bot Admin Only. [reason] is optional.

#admin #suggestions **Added Suggestion by Slam - [reason]**
`>> shutdown [reason]`
	Shuts the bot down. Bot Admin Only. [reason] is optional.

#user-commands
`>> ticket`
	Opens a thread where moderators can address an issue.

#admin #suggestions **by Slam**
`>> chw [channel-id]` (alias)
`>> channelWhitelist [channel-id]`
	Whitelists a channel for the bot to not monitor

#admin #suggestions **by Slam**
`>> chs [channel-id] [bot | logs | art]` (alias)
`>> channelSettings [channel-id] [ bot | logs | art]`
	Sets a channel if it is either a bot-commands channel, a log channel, or an art-gallery channel.