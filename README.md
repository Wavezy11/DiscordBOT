# Discord Bot Setup Guide  

This repository provides the basic setup for a Discord bot, including the core `index.js` file. Follow the instructions below to complete the setup and get your bot running.  

---

## Prerequisites  

Before starting, ensure you have the following:  

- A **Discord account** (create one if you don't have it yet).  
- **Node.js** installed on your computer (check by running `node -v` in your terminal or CMD). If not installed, download it from [Node.js](https://nodejs.org).  
- A code editor such as **Visual Studio Code**.  

---

## Setup Instructions  

1. **Clone the Repository**:  
   ```bash
   git clone https://github.com/your-username/your-repo-name.git
   cd your-repo-name
   ```  

2. **Install Dependencies**:  
   Open a terminal in the project folder and run the following commands:  
   ```bash
   npm install discord.js@13
   npm install dotenv
   ```  

3. **Set Up Your Bot Token**:  
   - Go to the [Discord Developer Portal](https://discord.com/developers/applications).  
   - Create a new application and navigate to the **Bot** section.  
   - Reset your bot token and copy it.  
   - Create a `.env` file in the root of the project and add the following line:  
     ```env
     BOT_TOKEN=your-bot-token-here
     ```  

4. **Modify `index.js` to Use `.env`**:  
   The included `index.js` file already supports `.env`. Ensure this line is present:  
   ```javascript
   require('dotenv').config();
   const token = process.env.BOT_TOKEN;
   ```  

5. **Run the Bot**:  
   - Start your bot using:  
     ```bash
     node index.js
     ```  
   - If everything is set up correctly, the bot should log "Bot is online!" in your terminal.  

6. **Invite the Bot to Your Server**:  
   - Generate an OAuth2 URL from the Developer Portal.  
   - Paste the URL into your browser, select your server, and click **Authorize**.  

---

## Testing the Bot  

In your Discord server, type the following commands to test the bot:  

- `!ping`: The bot should respond with `Pong!`.  
- `!ding`: The bot should respond with `Dong!`.  

---

## Adding More Commands  

To add more commands, modify the `index.js` file. For example:  

```javascript
if (command === 'hello') {
    message.channel.send('Hello, world!');
}
```  

Typing `!hello` will prompt the bot to reply with "Hello, world!".  

---

## License  

This project is licensed under the [MIT License](LICENSE).  
See the LICENSE file for more details.  

---

### Repository Contents  

- **`index.js`**: Core script for the Discord bot.  
- **`.env`**: File for storing your bot token (not included, must be created).  
- **Other Files**: You must install dependencies like `discord.js` and `dotenv` using `npm install`.  

