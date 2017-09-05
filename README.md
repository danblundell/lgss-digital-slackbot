# LGSS Slackbot

This is a bot for helping administrate a shared slack channel for the LGSS Digital.

It's pretty unofficial, and just automates a few tasks where automating is useful. It's maintained by @danbludnell and a rip of the xgovslackbot by @bruntonspall

## Running your own copy

You'll need a few things:

1. A slack domain, I use a test channel, feel free to create your own or ask politely for access
2. A bot integration
3. A bot api token

### Create a slack domain

Just go to slack.com and create a new slack instance or use the test channel in the LGSS slack team.

### Creating a bot integration

Now make a bot integration inside of your Slack channel. Go here:

https://my.slack.com/services/new/bot

Enter a name for your bot. Make it something fun and friendly, but avoid a single task specific name. Bots can do lots! Let's not pigeonhole them.

When you click "Add Bot Integration", you are taken to a page where you can add additional details about your bot, like an avatar, as well as customize its name & description.
Copy the API token that Slack gives you. You'll need it.

## Starting it up

You'll want to run the following command
```node index.js```
or in development, run the following to have nodemon manage auto restarts on file change:
```nodemon index.js```

Your bot should appear on the slack channel and you should be able to interact with him/her/it as expected

# Using the bot

On the LGSS Slack team, the bot is called LGSS Digital bot and it's pronouns are it/it's/it's.

It can do two main tasks.

## Inviting people to join

Our slack is limited to LGSS Digital employees, but slack restricts invites to admins, so the bot can issue per user invites.  You can simply message it with `invite email@address` and it will send an invite, providing the email address is valid.

You can either message the bot direct, or address is in a channel, like `@lgssdigital_bot invite dan@email.com`.  It will reply in a thread to say it has sent the invite.

Currently invites are only sent to people with email addresses ending `.gov.uk`.

## Making an announcement

Slacks current system allows either everyone to make announcements everywhere, or only the admin to make announcements everywhere.

LGSSDigital_Bot has the power to make announcements in select channels, simply say, in channel, `@lgssdigital_bot announce` then type your message. @lgssdigital_bot will follow up with `@channel some words here (via @lgssdigital_bot)` with your name.  This makes the identity of the user explicit and clear.

This is only enabled for certain channels, so to enable it for a new channel, simply say `@michaelbotspall channel_announce #general on` and it will enable announcements in #general.  To turn announcements off, say `@lgssdigital_bot channel_announce #general off` and it will do so.

# Other features

LGSSDigital_Bot has a few other features:

* User roles, simply say `@lgssdigital_bot set role for @user to admin` to grant admin roles to a user.  Only super users can do this, and only admins can toggle channel announcements
* Uptime, simply say `@lgssdigital_bot uptime` and it will tell you how long it has been running
* Politeness, simply say `@lgssdigital_bot hello` and it will say hello back
* Name calling, say `@lgssdigital_bot call me maybe` and it will call you `maybe` when it says hello :)

# Future feature ideas

We'd like to steal some features from https://handbook.18f.gov/slack/ and provide some helpful features in future, such as raising issues on github for documentation, arranging standups, reminders etc but that's all for the future.
