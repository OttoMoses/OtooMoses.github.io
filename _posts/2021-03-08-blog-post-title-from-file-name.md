# Async Battle Royale Project Pitch

This is a project I've attempted one or two times in the past but never managed to finish. My hope is that documenting the process on this blog will be the motivation I need to actually get it done. I'll be trying to reuse as much of the code from the previous attempt as possible but I know there are some pretty rough architecture choices in there so I'm expecting to even that to need some tweaks.

## The Pitch
The concept of this game is an asynchronous input, simultaneous resolution, turn based battle royal game played via social media. That's a lot of adjectives so I'll break down the concept a little more: The core gameplay is a turn based battle royale with very simple mechanics, each turn a player can move or shoot in one direction. At some time interval the game server will take all player moves, which can be submitted to a bot at any time before this time, and process them to figure out who gets shot and who moves where, then the bot will post an updated game map and players will have another time interval in which they can submit moves. 

## Technology
I'm going to be building this in C# because it's the language I'm most familiar with. The first bot will be a discord bot built using discord .net but if I build the game logic correctly I could add other ways to submit commands in the future like a twitter bot. If I want the bot to be able to run multiple games I'll want a good way to store data I'm thinking that I'll use a database on the backend, this has the added benefit of giving me a natural way to decouple the game logic and the bot logic: the bot or bots update a user's data in the database and the game logic pulls from that database when it needs to.

## Milestones
My proposed timeline is something like this:

 - A working version of the game logic that runs with artificially provided data
 - A version of the game that properly pulls data from the the source
 - A version of the discord bot that correctly writes the data to the database
 - A version of the discord bot that correctly posts the updated maps
## Possible Problems
I know I can write the game logic and I know I can do the database work because neither of those are too dissimilar from what I've done in the past. The discord bot part will be new to me but the documentation on discord .net seems solid so I believe I can learn that, but that's where I expect most of my issues.
