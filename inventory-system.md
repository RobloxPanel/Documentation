# Inventory System

ROBLOX Panel offers an inventory system similar to [Murder Mystery 2](https://www.roblox.com/games/142823291/New-Map-Murder-Mystery-2) and [Apocalypse Rising](https://www.roblox.com/games/1600503/Apocalypse-Rising).

## Getting Started
You will first need to enable the Inventory System. Head to Game Settings and click on ```Enable Inventory System```.

Once you are done you will have to create a new item schema.

## Item Schema
*TODO: Make a better explanation, I'm writing this at 2:55 AM.*
Every item has data that cannot be changed whenever a player gains an item.

Required Schema Data:
 - Item ID
   - The ID that the item should used while using the APIs associated with the Inventory System.
 - Name
   - The display name of the item
 - Description
   - The description of the item.

Optional Schema Data:
 - Developer Product ID
   - The ID of the developer product. When set this will allow the item to be bought using robux.

You can also have custom schema variables, you are not limited to the ones listed above.

## Item Data
Every Item Instance (An item that a player has) has data associated with it.

Item Data:
 - Item Inventory ID
   - The ID that is associated with the item instance. Will be used for most API calls.

Just like the Item Schema, you can have custom variables in the item data.

## Random Item Generator
*TODO: Make the explanation better.*
In some games like [Apocalypse Rising](https://www.roblox.com/games/1600503/Apocalypse-Rising) you can gain skins by buying a crate. The crate will then generate a random item out of a list. With the ROBLOX Panel Inventory System, you are able to create a random item generator and then give the random item generator to a player which will give a random item.

## Item Drops
Item Drops can be done by creating a Random Item Generator and then giving it at some point during game play instead of giving it when you open a "crate" or buy a "crate".