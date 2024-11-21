# Discord Bot Setup Guide

This README provides a step-by-step guide to create and set up a Discord bot. Follow the instructions carefully to build your bot and test it in your Discord server.

## Prerequisites

- A Discord account (create one if you don't have it yet).
- Node.js installed on your computer (check by running `node -v` in your terminal or CMD).
- Visual Studio Code or another code editor of your choice.

---

## Steps to Create a Discord Bot

1. **Create a Discord Application**:
   - Go to the [Discord Developer Portal](https://discord.com/developers/applications).
   - Click on **New Application** and give it a name of your choice.
   - Keep this tab open, as you will need it later.

2. **Create a Discord Server**:
   - Create a new server in Discord or use an existing one.
   - Name the server appropriately.

3. **Set Up OAuth2 Permissions**:
   - In the Developer Portal, navigate to **OAuth2** under the **Settings** menu.
   - Enable the required scopes and permissions:
     - Under **Scopes**, select `bot`.
     - Under **Bot Permissions**, select the necessary permissions (e.g., `Send Messages`, `Read Message History`, etc.).

4. **Generate an Invite Link**:
   - Scroll down on the **OAuth2** page to generate a URL.
   - Copy the URL and paste it into your browser.
   - Invite the bot to your server and grant it the required permissions.

5. **Prepare Your Development Environment**:
   - Verify Node.js installation:
     ```bash
     node -v
     ```
   - If Node.js is not installed, download and install it from [Node.js](https://nodejs.org).

6. **Set Up Your Project**:
   - Open **Visual Studio Code** (or another editor).
   - Create a new folder for your bot project.
   - Inside the folder, create a new file named `index.js`.

7. **Initialize the Project**:
   - Open the terminal in your project directory.
   - Run the following commands:
     ```bash
     npm init -y
     npm install discord.js@13
     ```

8. **Write Your Bot Code**:
   - Copy and paste the following code into `index.js`:
     ```javascript
     const { Client, Intents } = require('discord.js');
     const client = new Client({ intents: [Intents.FLAGS.GUILDS, Intents.FLAGS.GUILD_MESSAGES] });
     const token = 'YOUR_BOT_TOKEN';

     client.once('ready', () => {
         console.log('Bot is online!');
     });

     client.on('messageCreate', message => {
         if (!message.content.startsWith('!') || message.author.bot) return;

         const args = message.content.slice(1).trim().split(/ +/);
         const command = args.shift().toLowerCase();

         if (command === 'ping') {
             message.channel.send('Pong!');
         } else if (command === 'ding') {
             message.channel.send('Dong!');
         } else if (command === 'freedom') {
             message.channel.send('WHAT IS FREEDOM!?!??!?!??!?!');
         }
     });

     client.login(token);
     ```

9. **Get Your Bot Token**:
   - In the Developer Portal, go to the **Bot** tab.
   - Click on **Reset Token** to generate your bot token.
   - Replace `'YOUR_BOT_TOKEN'` in the code above with your token.

10. **Run the Bot**:
    - In the terminal, run:
      ```bash
      node index.js
      ```
    - If everything is set up correctly, the bot will log "Bot is online!" in the terminal.

11. **Test Your Bot**:
    - In your Discord server, type `!ping` in the chat.
    - The bot should respond with `Pong!`.

---

## Adding New Commands

To add more commands to your bot, include additional `if` statements in your `index.js` file. For example:

```javascript
if (command === 'test') {
    message.channel.send('This is a test command!');
}
```

Typing `!test` in the Discord server will result in the bot replying with "This is a test command!".

---

## Troubleshooting

- Ensure your bot's token is correct.
- Check that the bot has the necessary permissions in your server.
- Make sure Node.js and Discord.js are properly installed.

---

Happy coding! 🎉