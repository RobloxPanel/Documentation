# Api Documentation Layout

## RobloxPanel.Utility.DeveloperProductPurchased
*Type: Signal*

Called when a Developer Product is purchased by a player.

```
RobloxPanel.Utility.DeveloperProductPurchased:connect(function (receiptInfo)

end)
```

### Arguments
 - receiptInfo
   - The info of the product being purchased in a table. Uses the same format as [ReceiptInfo](http://wiki.roblox.com/index.php?title=API:Class/MarketplaceService/ProcessReceipt#ReceiptInfo_contents) in [ProcessReceipt](http://wiki.roblox.com/index.php?title=API:Class/MarketplaceService/ProcessReceipt).