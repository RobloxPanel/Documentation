# Utility

Roblox Panel gives some utilities which game developers can use.

*[List of Utility functions in Roblox Panel Lua Module]()*

## Developer Products
When using the Inventory System, you will most likely have to change how you handle developer products being purchased.

Instead of overwriting the callback in the ```MarketplaceService``` you will instead connect to the following event:

```
RobloxPanel.Utility.DeveloperProductPurchased:connect(function (receiptInfo)

end)
```

Arguments:
 - receiptInfo
   - The info of the product being purchased in a table. Uses the same format as [ReceiptInfo](http://wiki.roblox.com/index.php?title=API:Class/MarketplaceService/ProcessReceipt#ReceiptInfo_contents) in [ProcessReceipt](http://wiki.roblox.com/index.php?title=API:Class/MarketplaceService/ProcessReceipt).