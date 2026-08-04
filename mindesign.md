This is another aproeach to hearthland video game, but made simplier. It is video board game about colonization, resources, and churchillig throught the day. 
The goal of the game is to conquere the world, and dont loose hope. 

1. We create 3x3 matrix of nodes connected vertical and horizontal, but not diagonal. there should be 9 nodes, and 12 arms. Box setup, like keypad.
2. Node in center is our homebase, others are expansion. Nodes should be complex object, as they will have many properties. Maybe literally object, as they could have buildings, and pops, and units inside. 
3. Each node shoud have population value of 1-9. Center piece is our homeland and has default value of 9. 
4. Each arm has cost value, the inside cross arms has value cost 1-5, and outer ring borders has cost value 5-7. 
5. There are resources in the game: Timber, Grain, Tabaccoo. Our home node has 3 grain and 2 farms by default. Tabaccoo exists in quantity of 1-3, grain 2-7, timber 1-5. We roll it at game start. 
This definies maximum extraction from the node. But we need to build plantacion, sawmills, and farms. And put pops into it. 1 pop is 1 good. Building cost 2 coins. 
6. Coins is a currency. We can trade it for goods or buy some other things. 
7. For 2 timber and 2 coins we can build Brewery, which turns 1grain 1 timber into 2 whiskey. 
8. We can trade with the world. Grain and timber has initial world stock of 8. Whiskey and tabacoo 1. Cost to buy/sell: Grains 2/1; Timber 3/1, Tabacco: 4/2, Whiskey 5/3. We cant overflow global cap of 10 for each good. 
9. The game has turns. We click button to progress turn. 
10. Churchillmood: Starts at 10, each round it drops by 1. We can put tabaccoo for +1, or whiskey for +2. If it reaches 0 we loose. 
11. We start with 2 troops. troops can teleport on nodes we control, or we have sea connection. They could be trapped if we loose sea connection.
    They cost 2 grain 1 coin to recruit, and eat 1 grain a turn. If no grain then 1 coin.
     If no coin then -1 churchillmood.
13. We start with 1 ship. We can build more for 2 timber 1 coin. We can move ship on any arm which has connection to hearthland (center node). We can have multiple ships on arm but no benefit 1 is enought.
14. Each node has required troop count. Startsting node has 1. Others have 1-3. We need to place required number of troops to collect taxes and manage production.
15. Putting ship on lane cost us each turn coins of the value. But controlling node (land) gives us coins equal to pop. but it needs to be lane connected to hearthland, and occupied with suffiecient number of troops.
16. We can skip nodes. like we can have only center and corners. But we still need connect ship lanes. There should flags on nodes: suffiecient troosp True. and sealanesconnection True. If both true then we collect coins and goods.
17. When we occupy land we still needs to build sawmill and farms and plantacions and assign pops to extract it.
18. We can teleport ships to homeland so they will not pay cost, just wait for next order.
19. Turn Buttons commits all calculations of cost and maybe production.
20. We have infinite magazine where we collect resources, and we can teleport it. 

We start game with 1 ship, 2 troops, 10 coins, center node controlled. It has 9 pops and demand 1 troop. It has 3 max grain with 2 farms build, and 2 pops producing. Therefore we get 2 grain from it. 

Buildings:
Farm 1 coin
Sawmill 1 coin 
Plantacion 2 grain 1 coin
Brewery 2 timber 2 coins
Troop 2 grain 1 coin (maintain 1 grains turn)
Ship 2 timber 1 coin

Production
Sawmill (timber), Plantacion (tabbacoo), Farm (grain) all 1 per turn, but you need to put pops on it, and build it. And there is resources limit on each node. 
Brevery 2 grain+2 timber=2 whiskey

Turn Cost
Troops 1 grain
Ship lanes - value in coins from lane cost. 

Defeat:
When churchillmood reaches 0 we loose. It degredes -1 each turn. Tabbaccoo sacrifize +1, Whiskey sacrifize +2

Victory:
When we collect 6 nodes with troops and sealanes. And reach churchillmood to 9. 


