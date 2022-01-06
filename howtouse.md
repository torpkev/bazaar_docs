![Bazaar](/images/bazaar_logo.png)

# How to Use

[Home](https://torpkev.github.io/bazaar_docs)

Shops can be placed in any chest or barrel.

To create a store, hold the item you want to sell in your main hand.  Then run the command

    /shop create <amount to buy/sell> <buy price> <sell price>
    
Amount to sell would be how many of what you're holding is included in each transaction.  If you held a single piece of stone, but put 4 as the amount, each buy/sell would be for 4.  The amount you're holding does not matter.

The amount cannot exceed the maximum stack size of the item.

Buy price is how much players will buy the item from the shop for

Sell price is how much players will be paid by the store for the item

You should always set your buy price equal to, or higher than the sell price.  If setting them equal, keep in mind that each time the store sells an item, the server MAY tax you.  So if you bought 10x stone for $20 and sold 10x stone for $20, but the server is taking 10% tax, you'll be out $2 on every transaction if someone buys and sells.

If you don't want players buying from this shop, set buy price to 0.   If you don't want them selling to the shop, set sell price to 0.

### Clan Shops

If you have Myriad Clans and wish to create a clan shop, you can create a clan shop that will access the clan wallet directly.  You must be a member of the clan you are creating the shop for

    /shop create <amount to buy/sell> <buy price> <sell price> -clan
    
### Admin Shops

Admin shops are shops that can be placed that do not require any stock.  You can set them up to buy/sell as normal, but any income is not applied anywhere, and any money paid out by the shop is not coming from any source.

    /shop create <amount to buy/sell> <buy price> <sell price> -admin
    
### Server Shops

Server shops are very similar to Admin shops, but differ in that you can set up a Server Account in the config - any income/outgoings would be applied to the server account, and so would keep a 'closed' economy instead of generating money out of thin air.

Server shops CAN have infinite stock, if set up in the config.  Otherwise they need to be stocked in the same way a regular shop would be

    /shop create <amount to buy/sell> <buy price> <sell price> -server
    
### Cooldown Periods

If you want to prevent players from spamming stores, you can add a cooldown period to any shop by adding the following to the end of the /shop create command

    -c:<number of seconds>
    
    # Example, adding a 10 second cooldown to the shop:
    /shop create 1 10 2 -c:10
    
### Domain Integration

Domain is a land claiming and grief prevention plugin that contains 4 Bazaar specific flags that can be used to limit creating, removing, and using shops in Domain fields

        PREVENT_BAZAAR_BUY_BY_NONALLOWED
        PREVENT_BAZAAR_CREATE_BY_NONALLOWED
        PREVENT_BAZAAR_REMOVE_BY_NONALLOWED
        PREVENT_BAZAAR_SELL_BY_NONALLOWED
        
When these flags are active in the field, only people allowed to the field will be allowed to perform the appropriate functions

### WorldGuard Integration

Bazaar adds 4 new flags to WorldGuard that can be used to limit Bazaar use in WorldGuard regions

create-shop

This flag when set will either allow or deny creating Bazaar shops in the region

use-admin-shop

This flag when set will either allow or deny using Admin/server shops in the region

use-shop

This flag when set will either allow or deny using player shops in the region

use-clan-shop

This flag when set will either allow or deny using clan shops in the region

Note: You can change the name of these flags in the config file

If you wanted to create a specific shop for a player, you would apply create-shop ALLOW to members and add them as a member of the region.  You would leave use-shop as ALLOW for everyone.

There is also a configuration option for worldguard_only_shops.  When this is set to true, Bazaar will ONLY allow players to create shops when they are in a WorldGuard region (not including __global__).  Players in OP will still be able to create them outside of the region.
