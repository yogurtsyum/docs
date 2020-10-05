# Qbot VPS Setup Guide
👋 Welcome! These setup instructions are specific for people who are hosting qbot on their own VPS.

❤️ **Please support qbot by subscribing to the creator's Youtube channel. It's free and helps them grow their channel tremendously.**   
➡️ https://youtube.com/c/Lengo

## 🖥️ Download the dependencies. (part 1)
There is some software you'll need to install on the host machine to follow this setup guide. They are listed below.

- [Node.js & npm](https://nodejs.org/en/download/)
- [Git](https://git-scm.com/downloads)

## ➕ Clone the bot.
Begin by heading to your VPS' console and install the latest version of qbot by running this command: `git clone https://github.com/yogurtsyum/qbot.git`

Next, head to the qbot directory by running this command: `cd qbot`

## 🔍 Download the dependencies. (part 2)
Next you'll need to install the dependencies. To do this, run the command `npm i`.

## 🚀 Start editing the config.
To do this, create the `.env` file.

Then, paste the text below into the file:

```
token=
prefix=
cookie=
groupId=
maximumRank=
logchannelid=
shoutchannelid=
```

Then fill out the fields. There are instructions below for what to put for each field.

### 🔑 token
To find this, head to https://discordapp.com/developers and login with Discord (if prompted to). Then click New Application at the top right. 

![Example](https://i.gyazo.com/7d2119ba9f7dd9396c976b3a14d0e293.png)

Pick an application name. This can be anything, like "(group name) Ranking Bot". 

![Example](https://i.gyazo.com/02a7c670e1edf6de136512a380581043.png)

Click "Create" after you picked the name.

![Example](https://i.gyazo.com/b749bc0e59dc15e2f91f36ef3225f436.png)

Now you are on your application's setting page. Click Bot on the side. 

![Example](https://i.gyazo.com/db62b68cf165fe00cee73372245e35f4.png)

At the top right, click Add Bot.

![Example](https://i.gyazo.com/6a9f92e47cedebc803ab886a68807bd4.png)

Then click Yes, do it. 

![Example](https://i.gyazo.com/2bb4da3f0e990fa3e0471792076e0e40.png)

You now have a bot account! Now make sure you **disable** Public Bot so only you can add the bot to a server.

![Example](https://i.gyazo.com/f18e30f510204a91f8f36b72553b749a.png)

The next step you have to do is copy the token. To do this, click Copy under Click to Reveal Token.

Please note that by sharing this with qbot, you are giving the qbot code full access to the bot account you just created. Never share your token with anyone! It gives them full access to your bot account. 

![Example](https://i.gyazo.com/a6f0d065d94470b965b7e36fc4eb144f.png)

### 🏷️ prefix
What do you want to be the prefix for your commands? It can be anything.

### 🍪 cookie
To find this, you need to create a bot account at https://roblox.com in an incognito tab (because logging out invalidates the cookie) and give it a rank that can manage roles in your group. Then, right click anywhere and click Inspect Element or Inspect. At the top of the code that popped u you will see some tabs like Elements and Console. For this, you will need to go to Application. If you don't see it, click the >> and then Application. Then, on the left side of the Inspect Element popup, click the arrow by Cookies. Then, select https://web.roblox.com - you will then see some information. Next, copy the value of .ROBLOSECURITY.

Please note that by sharing this with qbot, you are giving the qbot code full access to the bot account you just created. Next, do not log out of Roblox. Simply close the tab. Once you start qbot, you will be automatically logged out of the bot account. Never share your cookie with anyone! It gives them full access to your bot account.

### 🍭 groupId
To find this, go to your group page and copy the small string of numbers in the link.
### 🔢 maximumRank
What do you want the maximum rank number that qbot can rank to, to be? It can't be above the Roblox bot's rank number.
### 📜 logchannelid
If you don't want a log channel, type "false". Otherwise, follow the following instructions to set a log channel.  
To do this you will need to first enable Developer Mode if it isn't already by first going into User Settings.

![Example](https://i.gyazo.com/29406bfb9a428854639d53f002994901.png)

Then go to Appearance on the left sidebar.

![Example](https://i.gyazo.com/6562a46e4197ea4964af2f994345dd15.png)

Next, enable "Developer Mode" at the bottom.

![Example](https://i.gyazo.com/b8d0de9060355795217428558bd3a6c3.png)

Next, exit out of settings right click on the channel you'd like qbot to log ranking actions in and click Copy ID.

![Example](https://i.gyazo.com/185225fded6e3a7eeba6936c08ebc46f.png)
### 📣 shoutchannelid
Follow the same instructions as the previous step "What is the Discord log channel ID?", but instead of right clicking the ranking log channel, right click the channel you'd like qbot to log shout messages in.

## 🚪 Invite your bot.
Inviting the bot is easy. Just head back to the application page on https://discordapp.com/developers and click OAuth2 on the side. 

![What to click](https://i.gyazo.com/e043e1c5049226c972960c5bb299c399.png)

Then, if you scroll down you will see Scopes and a ton of check boxes. Check the "bot" box so there is a check mark in the box.

![What to click](https://i.gyazo.com/3ada0791a75b28ed02336db0c04cc58c.png)

Then scroll down to "Bot Permissions" and select the permissions you would like the bot to have. Note that if you don't give the bot the "Administrator" permission, you will need to make sure the bot has access to the channel that it has to respond to commands in.

![Example](https://i.gyazo.com/d4ad6d95a2e25709df74bfdbc58df8ca.png)

Next, you can look at the bottom of scopes and head to the link it shows to invite the bot.

![Example](https://i.gyazo.com/f6b1136836d4c87005f802e65dda5e3e.png)

Once you head to that link, you will be prompted to choose what Discord server you would like to add your bot to.

![What to click](https://i.gyazo.com/7b7e2551a01c01f950880ba23c37d809.png)

Click "Continue" once you choose the server:

![What to click](https://i.gyazo.com/6c1ac2abd4fb13e02b644a887cab2bd0.png)

Confirm the permissions you are giving the bot and click "Authorize" to add the bot to your server.

![What to click](https://i.gyazo.com/fe8a80f1a07c5b9b2fe1ee0e977fc26b.png)

The bot is now in your server!

## 🗺️ Change the port
Head to the bottom of the `index.js` file and change the `process.env.PORT` variable to the port you'd like the bot to run on. You can also just remove the Express server.

## 🌅 Launch the bot
Start the bot with `node index.js`. You can also use an NPM Module like `pm2` to keep the bot online at all times.

## 🎉 Congratulations! qbot has been setup!
Congratulations! You just set up an instance of qbot for yourself. Now, go test it out! If you encounter any issues, please do not hesitate to join our support server and ask for support. We will be happy to help you resolve the issue.  
Support Server: https://discord.gg/J47m7t4

## 🎮 Optional: Change your bot's activity.
You can change your bot's activity by editing the `bot-status.json` file. First replace the `false` to `true` on the second line to enable the activity feature under the `activity` option. Then you can replace the `PLAYING` on the third line under the `activitytype` option to either `PLAYING`, `STREAMING`, `LISTENING`, or `WATCHING`. Then change the `Roblox` on the fourth line under the `activitytext` option to the activity text (playing ...). Finally, (only if you set `activitytype` to `STREAMING`) change the `https://twitch.tv/roblox` on the fifth line under the `activityurl` option to the URL of the Twitch stream.

## 🔨 Discord API TOS
Please note that Discord has a TOS for its API: https://discord.com/developers/docs/legal

This TOS is being updated August 15th, 2020 and will require all bots to have a privacy policy (even if it just says you don't collect personal information and has a way to contact you with any privacy concerns). qbot does not have this built in so you will need to add this yourself. 

More info can be found on the [Discord Developers](https://discord.gg/discord-developers) server in [this](https://discord.com/channels/613425648685547541/697489244649816084/728031320625905794) message.

## 📚 Thanks for reading!
While you are at it, please subscribe to my Youtube channel. If you need any help with qbot, feel free to join my Discord server.   
Discord: https://discord.gg/J47m7t4  
Youtube: https://www.youtube.com/c/Lengo   
If you need any help, there are a ton of helpful people on my Discord that can help you out.
