# mongo-ecoglob

# What is 'mongo-ecoglob'
>```
>It is a global economy package that allows you to create, delete, edit data for the user and much more
>```

# Why mongo-ecoglob?
>```
>- Easy to use
>- Uses mongo databases which are encrypted
>- Provides a global economy system
>- Has a bank system
>- Has a bank limit
>```

# Bug reports

[![](https://media.discordapp.net/attachments/823572003625369631/865336387309404190/e7ab03bac23eb9b3f5bd67ba27ca7b08.gif)](https://discord.gg/BgbXymBReQ)

### Package Made by: `Benzian10k#5088`.

# Setting up
>```
>Here is the basic code to connect to your mongoDB
>```

### mongoDB URI Setup
>```
>const { setURI } = require("mongo-ecoglob");
>setURI("You mongoDB URI");
>```

**Increasing the value of bank limit by a bit each time the author sends a message**
>```
>const { findUser, createProfile, incBankLimit } = require("mongo-ecoglob");
>client.on("message", async (message) => {
>  if (!message.guild) return;
>  if (message.author.bot) return;
>  const randomValue = Math.floor(Math.random() * 9) + 1;
>  const user = await findUser(message.author.id);
>  if (!user) return await createProfile(message.author.id);
>  if (user) return await incBankLimit(message.author.id, randomValue); //using the function to inc bank limit
>});
>```

**Bal command**
>```
>const {
>  findUser,
>  getCoinsInWallet,
>  getCoinsInBank,
>  getBankLimit,
>} = require("mongo-ecoglob");
>const Discord = require("discord.js");
>const target = message.mentions.members.first() || message.member;
>const user = await findUser(target.id);
>if (!user) return message.channel.send("You dont have a profile");
>const coins = await getCoinsInWallet(target.id);
>const bankCoins = await getCoinsInBank(target.id);
>const bankLimit = await getBankLimit(target.id);
>const embed = new Discord.MessageEmbed().setTitle("Balance").addFields(
>  {
>    name: "wallet",
>    value: coins,
>  },
>  {
>    name: "bank",
>    value: bankCoins + "/" + bankLimit,
>  }
>);
>message.channel.send(embed);
>```

**setURI**
>```
>setURI(<mongoDB URI: string>);
>```
This is used to connect to the mongoDB

**findUser**

>```
>findUser(<userID: string>);
>```
This is used to find if there is an entry in the db for a certain user

**createProfile**

>```
>createProfile(<userID: string>);
>```
This is used to create a profile if the user dosnt have one alredy


**deleteProfile**

>```
>deleteProfile(<userID: string>)
>```
This is used to delete profile of the user if they have one

**getCoinsInWallet**

>```
>getCoinsInWallet(<userID: string>)
>```
This is used to get the value of coins for the target

**incCoinsInWallet**

>```
>incCoinsInWallet(<userID: string>, <coins: Number>)
>```
This is used to increase the value of coins for the target

**decCoinsInWallet**

>```
>decCoinsInWallet(<userID: string>, <coins: Number>)
>```
This is used to decrease the value of coins for the target

**getCoinsInBank**

>```
>getCoinsInBank(<userID: string>)
>```
This is used to get the value of bank for the target

**incCoinsInBank**

>```
>incCoinsInBank(<userID: string>, <coins: Number>)
>```
This is used to increase the value of bank for the target


**decCoinsInBank**

>```
>decCoinsInBank(<userID: string>, <coins: Number>)
>```

This is used to decrease the value of bank for the target

**getBankLimit**

>```
>getBankLimit(<userID: string>)
>```

This is used to get the value of banklimit for the target

**incBankLimit**

>```
>incBankLimit(<userID: string>, <value: Number>)
>```

This is used to increase the value of banklimit for the target

**decBankLimit**

>```
>decBankLimit(<userID: string>, <value: Number>)
>```

This is used to decrease the value of banklimit for the target
