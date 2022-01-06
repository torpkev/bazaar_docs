![Bazaar](/images/bazaar_logo.png)

# Commands

[Home](https://torpkev.github.io/bazaar_docs)


### Create a new shop

Hold the item you wish to sell in your main hand, then issue the command.  The amount entered in the command is the buy/sell amount, the amount you're holding is not considered.

If you want the store to buy and not sell, enter the price for buy, but 0 for sell.  Vice versa if you want to sell and not buy.  Enter a price for both if you want to both buy and sell.  Buy and sell price is from the point of view of the customer.

Requires bazaar.create permission for player stores.

Requires bazaar.create.admin permission for Admin stores

Requires bazaar.create.server permission for Server stores

Requires bazaar.create.clan permission for clan stores, also requires Myriad Clans is required for clan stores, and you must be a member of the clan

    /shop create <amount> <buy price - 0 for not buying> <sell price - o for not selling> -admin (optional) -server (optional) -clan (optional) -c:<seeconds> (optional)

#### Examples:

    /shop create 4 10 4 - This would create a store that sells 4 of the item for $10, or buys 4 for $4
    /shop create 1 200 0 - This would create a store that sells for $200 and does not buy back
    /shop create 1 0 100 - This would create a store that buys for $100 and does not sell back
    /shop create 1 20 2 -c:10 - This would create a store that sells 1 item for $20 and buys back for $2, and implements a 10 second cooldown between transactions
    /shop create 1 100 0 -admin - This would create an admin store that sells 1 item for 100 and does not buy back. Admin stores do NOT need any inventory in the chest.
    /shop create 1 100 0 -clan - This would create a clan shop that sells 1 item for $100 and does not buy back. Payments are made to and from the clan wallet directly

### Remove an existing shop

Used to remove an existing shop.

Requires bazaar.remove to remove your own player shop or clan shops for your clan

Requires bazaar.remove.admin to remove admin shops

Requires bazaar.remove.server to remove server shops

bazaar.admin will allow you to remove any shop, regardless of ownership or type

    /shop remove

### Cancel a new shop/remove shop command

Used to cancel an existing create new shop or remove shop command.  These commands typically run for 15 seconds, using cancel will let you exit it early. 

    /shop cancel

### Get the current version

Gets the current version of the plugin

    /shop version

### Toggle debug mode

Toggles debug mode on/off

Requires bazaar.admin

    /shop debug

### Reload config/stores

Reloads the config file and stores from file

Requires bazaar.admin

    /shop reload
