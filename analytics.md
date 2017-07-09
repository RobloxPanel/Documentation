# Analytics
One of Roblox Panel's main features is analytics. Analytics allows for Game Creators to track events and data within their Game.

For some analytics that you want to collect, it will require a bit of Lua scripting knowledge and having the [Roblox Panel Lua Module]() in the Place/Game.

*[More info for Lua implementation of Analytics]()*

## Events
*Show image/gif of the events panel*

Events are a type of analytic data that involves time.

Events will have having the following data that can/have be attached: (Any item in the list that does not have *(Optional)* next to it is required.)
 - Time called
 - Name of Event
 - Extra Data (Optional)

### Extra Data
The extra data is in [JSON](http://wiki.roblox.com/index.php?title=JSON), which in ROBLOX is represented as a [Lua Table.](http://wiki.roblox.com/index.php?title=Table)

The valid data types that can be used in the extra data are:
 - [String](http://wiki.roblox.com/index.php?title=String)
 - [Number](http://wiki.roblox.com/index.php?title=Number)
 - [Boolean](http://wiki.roblox.com/index.php?title=Boolean)
 - Array (In Roblox Lua this is represented as a [table](http://wiki.roblox.com/index.php?title=Table) that has only incremental indexes i.e 1,2,3,4,5,...)
 - Null (Same as [Lua's nil](http://wiki.roblox.com/index.php?title=Nil))
 - Object (In Roblox Lua this is represented as a [table](http://wiki.roblox.com/index.php?title=Table) that only has string indexes)

Roblox Objects cannot be passed through JSON, if you want to pass in a Player object you should pass in the Player's Id (```Player.UserId```).

#### Json Example
```
{
    "VictimPlayerId": 20,
    "KillerPlayerId": 20
}
```

### Implementation without Lua
Event analytics that require no lua scripting knowledge to enable include:
 - A Player Dies
 - A Player Joins
 - A Player Leaves

To enable an event analytic that doesn't require lua scripting you will need to *TODO: Setup process to enable events without lua*.

## Player Variables
*Show image/gif of the player variables panel*

Player Variables are a type of analytic data which is associated with a Player. Player variables can be used as a database for information such as Money, Points, Wins, or Losses. You can edit these variables through the web site or through the [Roblox Panel Lua Module]().

In order to set a Player Variable you must add it to the Player Variable schema. Which will then allow you set and get the player variable.

*[More info on using player variables in Roblox Lua]()*

### Valid Variable Types
 - [String](http://wiki.roblox.com/index.php?title=String)
 - [Number](http://wiki.roblox.com/index.php?title=Number)
 - [Boolean](http://wiki.roblox.com/index.php?title=Boolean)
 - JSON Array
 - JSON Object

### Implementation without Lua

Player Variables that require no lua scripting knowledge to enable include:
 - Death Count

To enable a player variable that doesn't require lua scripting you will need to *TODO: Setup process to enable player variable types without lua*.