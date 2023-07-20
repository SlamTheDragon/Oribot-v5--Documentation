
## Moderator Commands 
These are the moderator commands as listed on #Commands #command-handling 


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
	
`>> chw [channel-id]` (alias)
`>> channelWhitelist [channel-id]`
	Whitelists a channel for the bot to not monitor

`>> chs [channel-id] [ bot | logs | art ]` (alias)
`>> channelSettings [channel-id] [ bot | logs | art ]`
	Sets a channel if it is either a bot-commands channel, a log channel, or an art-gallery channel.