# Server Administration

ROBLOX Panel allows for server administration through a web interface. You can ban, kick, broadcast messages, and look at chat (which can be unfiltered).

## Server Information
The server page will show the following information:

*Put a image of the server informations here.*

 - (a) Player List
 - (b) Player Count
 - (c) Max Players
 - (d) Perferred Player Count

## Banning Players
*Put an image/gif of the player banning process*
You are able to ban players from your game through the web interface. You can give a reason why you banned the player.

When banning a player, make sure you think about why you are banning this player and if you really should. A couple of good reasons to ban someone is if someone swears in your game, someone cheats. If you are banning someone because they think you game is bad, it could give a bad impression that you cannot take criticism and people will possibly not play.

## Kicking Players
*Put an image/gif of the player kicking process*
You are able to kick players from your game through the web interface. You are able to give a reason why you kicked the player.

## Broadcast a Message
*Put an image/gif of broadcasting a message*
You are able to send a message that will be shown to all players in the server.

You can specify where the message shows up:

 - Chat
 - Center Message

The filter's ```fromUserId``` context will be the person who sent the broadcast message. The message will also be filtered with the [TextFilterResult:GetChatForUserAsync](http://wiki.roblox.com/index.php?title=API:Class/TextFilterResult/GetChatForUserAsync) function as accordingly.

### Custom Center Message Gui
If you want to implement the Center Message sending, you will need to first set the following variable to false on the client side:

``` RobloxPanel.ServerAdministration.UseDefaultCenterMessageGui = false ```

This variable will disable the default center message gui. Then you will need to connect to this event on the client side:

```
RobloxPanel.ServerAdministration.WebCenterMessageSent:connect(function (message)
    -- The message will be filtered but if you want to filter it once more you can, although it is not recommended.
end) 
```

Arguments:
 - message (String)
   - The message sent from the web interface which is filtered through ROBLOX's filter using [TextFilterResult:GetNonChatStringForBroadcastAsync](http://wiki.roblox.com/index.php?title=API:Class/TextFilterResult/GetNonChatStringForBroadcastAsync).

## Look at Chat
*Put an image/gif of the chat panel*
You can look at the server chat through the web interface.

When ever someone chats it will show the message, the time it was sent, the user that posted it, and if it is a whisper and if it is who is it to.

You can also broadcast a message through this part of the interface as well.

You are able to look at the messages unfiltered, however to do this you will need to enable the option to show the unfiltered message.

``User Settings -> Can See Unfiltered Messages``

Then to see a message unfiltered when you enabled seeing them, click on the message you want to see unfiltered and it will change to the unfiltered version. 

*Put an image/gif of showing an unfiltered message. Let's try and keep this PG if possible*

### Implementing web chat feataures
If you have a custom chat gui or you want to have a custom chat gui, you will need to call the following function in the [Roblox Panel Lua Module]() whenever a player sends a message.

```
RobloxPanel.ServerAdministration:SentChat(playerSent, playerSentTo, nonFilteredMessage)
```

Arguments:
 - playerSent (Player object)
   - The player who sent the message
 - playerSentTo (Player object)
   - The player who recieved the message, if everyone recieved this message pass in nil.
 - nonFilteredMessage (String)
   - The message that the player sent, without applying the ROBLOX text filter. If the message was whispered the text filter applied will be 

To implement the web interface sending a chat to a server, you must connect to the following event:

```
RobloxPanel.ServerAdministration.WebSentMessage:connect(function (message)
    -- The message will already be run through the text filter, but if you want to you can run the filter again (although not recommended).
end)
```

Arguments:
 - message (String)
   - The message that was sent from the web interface which is filtered accordingly using [TextFilterResult:GetChatForUserAsync](http://wiki.roblox.com/index.php?title=API:Class/TextFilterResult/GetChatForUserAsync).