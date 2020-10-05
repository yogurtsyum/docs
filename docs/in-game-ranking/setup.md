# In Game Ranking Setup Guide
👋 Welcome! These instructions include setup + hosting for In Game Ranking.

❤️ **Please support qbot by subscribing to the creator's Youtube channel. It's free and helps them grow their channel tremendously.**   
➡️ https://youtube.com/c/Lengo

## 🌵 Create a repl.it account.
First step is to create an account at [https://repl.it](https://repl.it). To do this, head to [https://repl.it/signup](https://repl.it/signup) and sign up.

## ➕ Create the In Game Ranking repl and download the project code.
Once you've created an account at repl.it signed in to it, head to the home page at [https://repl.it/~](https://repl.it/~) and select "new repl" at the top right.

![Example](https://i.gyazo.com/6f69e635af6a4d778702a72e40548039.png)

Then set the language to "Nodejs" and click on "Create Repl".

![Example](https://i.gyazo.com/044630fb8d346bc4ae2a486430e7e031.gif)

Right click in the editor and click on "Command Palette". Then search and select "Open Shell".

![Example](https://i.gyazo.com/bdf5f8fc51237b01df9fbca76ecf4c28.gif)

Next, download In Game Ranking to your project in the shell (the bottom right of the screen) with `git clone https://github.com/yogurtsyum/in-game-ranking.git` and move the In Game Ranking files into your main app directory with `mv ./in-game-ranking/* ./`.

![Example](https://i.gyazo.com/6c85d57e77e9d33e2302d8f3c680a1f5.gif)

Finally, delete the unnecessary In Game Ranking folder by clicking the 3 dots to the right of the In Game Ranking folder under "Files" and selecting "Delete". When prompted, confirm deleting the folder by clicking "Yes, delete this folder".

![Example](https://i.gyazo.com/03659bd33b39e727f8c186e87f5fadbd.gif)

Congratulations! You have officially installed In Game Ranking onto your repl. Continue with the instructions below to set it up.

## 🚀 Start editing the config.
To do this, create the `.env` file by clicking the "Add file" icon to the right of "Files".

![Example](https://i.gyazo.com/3fe59b407d0121976b9dc536a7212ba5.gif)

Then, paste the text below into the file:

```
key=
cookie=
groupId=
logwebhook=
```

Then fill out the fields. There are instructions below for what to put for each field.

### 🔑 key
This is a secure and unique password that you create that will put in both the ranking server on the Glitch project and the Lua script. It is used to secure all requests and if someone knows it and the Glitch project URL they could use the ranking server to rank people. It is recommended that you generate this password so it can't be easily guessed. Never share your key with anyone.

### 🍪 cookie
To find this, you need to create a bot account at https://roblox.com in an incognito window and give it a rank that can manage roles in your group. Then, right click anywhere and click Inspect Element or Inspect. At the top of the code that popped u you will see some tabs like Elements and Console. For this, you will need to go to Application. If you don't see it, click the >> and then Application. Then, on the left side of the Inspect Element popup, click the arrow by Cookies. Then, select https://web.roblox.com - you will then see some information. Next, copy the value of .ROBLOSECURITY.

Please note that by sharing this with In Game Ranking, you are giving the In Game Ranking code full access to the bot account you just created. Next, do not log out of Roblox. Simply close the tab. Never share your cookie with anyone! It gives them full access to your bot account.

### 🍭 groupId
To find this, go to your group page and copy the small string of numbers in the link.

### 🔢 maximumRank
The maximum rank number that In Game Ranking can rank to. It can't be above the Roblox bot's rank number.

### 🔗 logwebhook
The Discord Webhook URL to send ranking logs to. You can create this by going to the log channel in Discord, clicking the gear icon, and then going to the "Integrations" tab.

![Example](https://i.gyazo.com/04cb5c17c8cdb5cbb845c44513e35d3d.png)

Then click "View Webhooks" or "Create Webhook" depending on which one is shown.

![Example](https://i.gyazo.com/8ce77fde7c616e97146c1a6299f57361.png)

If you weren't already prompted to create a webhook, click "New Webhook".

![Example](https://i.gyazo.com/9146f12b6df9e67272218ea8a0e5d69b.png)

Finally, click "Copy Webhook URL" and then paste it into the config file. You can optionally customize the webhook name and avatar.

![Example](https://i.gyazo.com/c9a5c145f89fb5cae73532166765e133.png)

Although people with the "Manage Webhooks" permission in your server/channel can access this Webhook settings and URL, do not share the Webhook URL with anyone that wouldn't otherwise have access because it lets them anonymously send messages to that channel.

If you'd like to disable this feature, type `false`.

## 📜 The Lua Script
Now, head to [https://github.com/yogurtsyum/in-game-ranking/blob/master/lua-script.lua](https://github.com/yogurtsyum/in-game-ranking/blob/master/lua-script.lua) and copy and paste that into the Server Script Storage of your Roblox game. At the top you have to change some settings for the script.

For each setting, there's a section below that will show you how to find what value to put for it.

### 🍭 groupId
To find this, go to your group page and copy the small string of numbers in the link.

### 🛡️ requiredRank
This is the minimum rank number that is needed to rank people in-game. 

### 🛎️ server
The repl in the format of `https://PROJECT_NAME--USERNAME.repl.co`. Replace the `PROJECT_NAME` in the URL with your repl's name (can be located at the near top left of the page). Replace the `USERNAME` in the URL with your repl.it username (chosen when you signed up).

## 🎉 Congratulations! In Game Ranking has been setup!
Congratulations! You just set up an instance of In Game Ranking for yourself. Now, go test it out! If you encounter any issues, please do not hesitate to join our support server and ask for support. We will be happy to help you resolve the issue.
Support Server: https://discord.gg/J47m7t4
