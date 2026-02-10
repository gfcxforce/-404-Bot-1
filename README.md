const Discord = require('discord.js');
const client = new Discord.Client({ intents: [32767] });
const http = require('http');

// Render'ın istediği o meşhur linki (Web Service) aktif eden kısım:
http.createServer(function (req, res) {
  res.write("Bot 7/24 Aktif!");
  res.end();
}).listen(8080);

client.on('ready', () => {
  console.log(`${client.user.tag} olarak giriş yapıldı!`);
});

// Botunun komutlarını buraya ekleyebilirsin
client.on('messageCreate', msg => {
  if (msg.content === 'ping') {
    msg.reply('Pong!');
  }
});

client.login(process.env.TOKEN);



{
  "name": "discord-bot",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "start": "node index.js"
  },
  "dependencies": {
    "discord.js": "^14.13.0"
  }
}
