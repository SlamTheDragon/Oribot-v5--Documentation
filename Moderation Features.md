#command-handling #permission-access #mod-commands #admin 

A brief explanation of how Moderation System works.


## Permission Levels
Here are the permission levels that the Oribot uses.
- New User `visitor`
- Validated User `member`
- Moderator `moderator`
- Bot Admin `admin`

See [Admin Commands](#Admin%20Commands), [Permission System](Permission%20System.md), and [Safety & Setup](Safety%20&%20Setup) on how to set user permissions.

```C#
// Perhaps document how this looks on code
```

# Command Usage 
The summary of the useful commands for moderators.

#mod-commands 
### Moderator Commands
`>> mute [User ID] [Reason] [Duration]`
	Mutes a user for the given duration, logs the mute, and DMs them with [Reason]. 

`>> unmute [User ID] [Reason]`
	Unmutes a user.

`>> warn [harsh, minor] [User ID] [Reason]`
	DMs the user with an automated warning, and logs it internally. 

`>> warnlog [User ID] [Entry Index]`
	Allows for viewing a user's log, or view a specified entry. 

`>> deletelog  [User ID] [Entry Index] [Reason]`
	Deletes the given log entry and logs a reason for deletion. 

`>> note [User ID] [Note Content]`
	Logs a note about a potentially problematic user. 

`>> ban [User ID] [Reason]`
	Bans the given user and DMs them with [Reason]. 

`>> addbadge [User ID] [Badge Name]`
	Adds a badge to a user's profile. 

#suggestions  **by Slam**
`>> closeticket [reason]`
	Closes a ticket opened by a user.

`>> approve [User ID] [reason]`
	Similar to `>> promote`, this command is designed for moderators to approve new-entry users from `visitor` to `member`. See [Permission System](Permission%20System) for more information.


#admin 
### Admin Commands
#suggestions **by Slam - added [reason]**
`>> restart [reason]
	Forces the bot to restart. Owner/Admin Only. [reason] is optional.

#suggestions **by Slam - added [reason]**
`>> shutdown [reason]`
	Shuts the bot down. Owner/Admin Only. [reason] is optional.

#suggestions **by Slam**
`>> chw [channel-id]` (alias)
`>> channelWhitelist [channel-id]`
	Whitelists a channel for the bot to not monitor. Owner/Admin Only.

#suggestions **by Slam**
`>> chs [channel-id] [bot | logs | art]` (alias)
`>> channelSettings [channel-id] [ bot | logs | art]`
	Sets a channel if it is either a bot-commands channel, a log channel, or an art-gallery channel. Owner/Admin Only.

#suggestions  **by Slam**
`>> promote [user-id] [admin | moderator | member | visitor]`*
	Promotes/demotes a user's permission level.


## Code Documentation
In-depth explanation of all commands n' stuff.

### Ticketing System
Description

```C#
// placeholder
```

[...]