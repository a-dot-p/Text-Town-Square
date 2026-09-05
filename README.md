<img width="641" height="725" alt="image" src="https://github.com/user-attachments/assets/c66b9c02-3ca4-41a1-958c-c1ed9ec87d93" />
<img width="522" height="417" alt="image" src="https://github.com/user-attachments/assets/4734a15f-0cfd-47e0-9d0c-c9ab966828b1" />

# Text Town Square
This is a tool to make playing long-term text games of Blood on the Clocktower on Discord easy to setup and run.

Credit goes to the [Carat](https://github.com/JackKBroome/Carat_BOTC) bot in the Blood on the Clocktower [unofficial server](https://discord.com/invite/botc) for the general formatting & structure of text games on Discord. Text Town Square contains many features modeled after existing Carat commands.  

The tool uses [YAGPDB](yagpdb.xyz) bot instead, eliminating the need for hosting. 

### Features
* built-in commands: all actions are integrated via buttons and menus. No text commands are needed
* run as many games as you want simultaneousyly
* recruit and set up seat order
* manage life & death status and dead votes
* nominate, vote, add accusations & defenses
* set hourly reminders, quickly message all players

# Setup

## 1) Add YAGPDB
If your server doesn't have it, add [YAGPDB](yagpdb.xyz). Go to [its control panel](https://yagpdb.xyz/manage) and go to Custom Commands. Make sure it has the appropriate permissions to add roles, create threads (including private), delete threads, send messages, etc. 

## 2) Add commands
You will need `4` command slots open to run Text Town Square (the max is 50 for free users). Add the 4 files from this repository like so:

### `1-setup`
 
 <img width="1132" height="306" alt="image" src="https://github.com/user-attachments/assets/84e32ff3-2fb4-4446-8f23-85fc3a8f5bea" />
 
 *Note: this uses a custom slash commmand. YAGPDB only allows 3 custom slash commands per server, so this will take 1 slot*

Above `Trigger type` there is a number (e.g. `#23`). Remember this for later.

`Command Trigger` can be whatever you want.


Setup the options like so:

<img width="1305" height="748" alt="image" src="https://github.com/user-attachments/assets/45052b21-4aae-4a60-a670-20fb49f72376" />


<img width="1377" height="715" alt="image" src="https://github.com/user-attachments/assets/03b702aa-e264-4afe-99a9-5492ac8fa521" />

Copy+Paste the code in the Response section.

**$\color{red}{\text{IMPORTANT:}}$** set the role restrictions at the bottom to **Mod** or **Admin** roles on your server. This command can be abused.


### `2-modal-creation`

Set this up *exactly* like below. Make sure trigger is `Message Component`
<img width="990" height="512" alt="image" src="https://github.com/user-attachments/assets/29784be5-cd81-42ad-bd7f-183421750d0e" />

Copy+Paste the code in the Response section.


### `3-response-set-one`
Set this up *exactly* like below. Make sure trigger is `Modal Submission`
<img width="920" height="527" alt="image" src="https://github.com/user-attachments/assets/25a3b86d-4646-4250-b999-92d6cd72a85c" />

`Name` can be whatever you want.

Copy+Paste the code in the Response section.

**$\color{red}{\text{IMPORTANT:}}$** Find `CHANGE_ME` in the code in `3-response-set-one`  and then replace it entirely with the number you found when creating `1-setup` (this is the custom command ID of that command). 


### `4-response-set-two`
Set this up *exactly* like below. Make sure trigger is `Modal Submission`
<img width="893" height="491" alt="image" src="https://github.com/user-attachments/assets/8d1d14ea-49f2-40fc-8740-bbc5eec3a6dc" />

`Name` can be whatever you want.

Copy+Paste the code in the Response section.

### Notes
* make sure the YAGPDB role is higher than all roles it needs to give
* this uses the built-in database to store info. If you are storing anything using the database, make sure its User ID is not the same as the channel ID of any games you are running, otherwise items may be deleted. Any other values will not be affected.
* do not forget to change `CHANGE_ME` when implementing `3-response-set-one

## 3) Creating a game
I. Create a new channel for your text game. Also, create a channel for the kibitz if needed. (a private chat with spectators).
II. Create a role for the Storyteller, players, and kibitz members. This can be an existing role, as long as no other text game is using them. 
III. Run the `/starttextgame` command (`1-setup`) to create the Town Square. (remember, this command should be Mod or Admin only). 
IV. Players can now join the game! The ST should select the start option when ready to begin.

### Notes
* most important guardrails are in-place, but you may see errors if an option was used incorrectly. Error messages are WIP.
* a nomination thread needs to be created to be able to nominate (through the menus)
* the end game commands deletes all database values related to the game. 







 
