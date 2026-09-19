<img width="529" height="199" alt="image" src="https://github.com/user-attachments/assets/2bb65fa7-43ee-452d-9825-735a32d788ec" />


<img width="641" height="725" alt="image" src="https://github.com/user-attachments/assets/c66b9c02-3ca4-41a1-958c-c1ed9ec87d93" />
<img width="522" height="417" alt="image" src="https://github.com/user-attachments/assets/4734a15f-0cfd-47e0-9d0c-c9ab966828b1" />

# Text Town Square
This is a tool to make playing long-form text games of Blood on the Clocktower on Discord easy to setup and run.

Credit goes to the [Carat](https://github.com/JackKBroome/Carat_BOTC) bot in the Blood on the Clocktower [unofficial server](https://discord.com/invite/botc) for the general formatting & structure of text games on Discord. Text Town Square contains many features modeled after existing Carat commands.  

The tool uses [YAGPDB](https://yagpdb.xyz) bot instead, eliminating the need for hosting. 

### Features
* built-in commands: all actions are integrated via buttons and menus. No text commands are needed
* send a shuffled bag of characters to all players
* run as many games as you want simultaneously
* recruit and set up seat order
* manage life & death status and dead votes
* nominate, vote, add accusations & defenses
* set hourly reminders, quickly message all players

# Setup

## 1) Add YAGPDB
If your server doesn't have it, add [YAGPDB](yagpdb.xyz). Go to [its control panel](https://yagpdb.xyz/manage) and go to Custom Commands. In Discord, make sure it has the appropriate permissions to add roles, create threads (including private), delete threads, send messages, pin messages, etc. 

## 2) Add commands
You will need `4` command slots open to run Text Town Square (the max is 100 for free users). Add the 4 commands either through the links below:

###  Setup
1. [Setup](https://yagpdb.xyz/cc/K1m-PrZ5xS)

     **$\color{red}{\text{IMPORTANT:}}$** set the role restrictions at the bottom to **Mod** or **Admin** roles on your server. This command can be abused.
 
3. [Modals](https://yagpdb.xyz/cc/zgwGXaaZPM)
4. [Responses #1](https://yagpdb.xyz/cc/ZWo3dI93oK)
5. [Responses #2](https://yagpdb.xyz/cc/bJd-69GBH1)


## 3) Creating a game
I. Create a new channel for your text game. Also, create a channel for the kibitz if needed. (a private chat with spectators).

II. Create a role for the Storyteller, players, and kibitz members. This can be an existing role, as long as no other text game is using them. 

III. Run the `/starttextgame` command (`1-setup`) to create the Town Square in the game channel. (remember, this command should be Mod or Admin only). 

IV. Players can now join the game! The ST should select the start option when ready to begin.

### Notes
* make sure the YAGPDB role is higher than all roles it needs to give
* this uses the built-in database to store info. If you are storing anything using the database, make sure its User ID is not the same as the channel ID of any games you are running, otherwise items may be deleted. Any other values will not be affected.
* most important guardrails are in-place, but you may see errors if an option was used incorrectly. Error messages are WIP.
* a nomination thread needs to be created to be able to nominate (through the menus)
* the end game commands deletes all database values related to the game & **cannot** be undone. 

***
# Actions Guide
## Players
### Town Square
`Join/Leave Game`: lets members join a seat and add a game nickname. To leave, use the same seat number and leave the name field blank. To change seats, leave and rejoin. A Storyteller thread is created for night actions (& deleted if the player leaves). 

`Whisper`: creates a private thread with the selected user for game day private chats. 

`Nominate`: creates a nomination in the nomination thread (must be made by the ST first) and adds the given accusation. Use the action menu on the nomination for voting.

`Set Status`: mark yourself as dead, and remove your vote token ("ghost vote"). The Storyteller can override your status if needed.

### Nominations

`Vote`: updates your vote statement in the nomination. Check the private vote option to hide your vote and not update the nominatino. 

`Add Defense`: lets the nominee add/update their defense statement.

## Storyteller
### Town Square
`(ST) start game!`: select to start the game with current players list. REQUIRED for in-game actions like nominations and voting. Players can't be added after this point.

`(ST) create Nom thread`: creates the current day's nomination thread. Nominations can't be made without this first. 

`(ST) add/remove to kib`: adds the selected members to the kibitz channel, and removes the selected members currently in it.

`(ST) set reminder`: set a reminder to ping the game role at hourly intervals. To send the message "The game ends in 2 hours!" for a 24-hour game day, set "Total time" to 24 and "Remind players that ..." to 2. Resubmit this for each reminder (4 hours left, 6 hours left ...)

`(ST) send to threads`: sends the given message to all ST threads. 

`(ST) send characters`: randomly assign the list of characters. Separate characters per line & use the official spelling. Select the channel to send the final list of characters to (kibitz, if you have it). Check the box to spoiler the name & image. This will work with non-official characters, though images won't work. 

`(ST) end game`: deletes all data stored for the game, removes player & your ST role. Cannot be undone. 

### Nominations
`(ST) count votes`: lets you tally the votes for each nomination. Private votes will show up at the top of the display, if any. Public votes are the same as on the nomination. Format like so: `1;1;1;0` where each number is how many it counts vor (ie. '1' for yes, '0' for no, other numbers for special characters like Banshee, Thief)














 
