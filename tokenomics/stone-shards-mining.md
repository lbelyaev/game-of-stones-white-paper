# Stone Shards Mining

Stone Shards, being parts of the original foundational Stones, are scarce by definition. In order to simulate the increased difficulty of mining them over time, we will use an artificially-programmed difficulty function (analog to what Bitcoin uses).

![Stones Shards Mining Over Time](https://lh3.googleusercontent.com/b2N5ruqT1QZA7glQjrhKC2DG0WlfRxAIyfv7qMl5krlQEaFgd6TbZbnJ5mO3Cl93cDH-iwMv7\_dkd6A0g3\_cdo\_yhtJPw6gYLHH9nF-x6UzveCYcYMBlb7Xxyy-U1P2RTyYbOyfk)

Given that distribution, the amount of Shards that could be mined in each period (epoch) is shown in the table below.

![](https://lh5.googleusercontent.com/PMqtutbEP5Mne15KvLQlc56qHM74VhqSNzkUaFv2I7ogu86s593bArQ-ntnGIn7nCZ8VzvKyfbjhqOPfBvY7rV8peWyYEIDg-yUWspenj6Fj6T1K7WXCqZGfQpvCbVUKSWPLnJVJ)

The actual mining of Stone Shards will be subject to the limits set in the table above and the following additional conditions:&#x20;

* Stone Shard size varies from 1 to 50 (step of 1)&#x20;
* In order to level mining output while moving from early to later epochs, mining interval is introduced, which starts at 1 block in epoch 1, increases to 131,072 blocks by epoch 18 and stays constant since then and until the final mining epoch 23&#x20;
* Average size of a mined Stone Shard (item) is targeted starting from 24 and decreasing gradually to 2 in epoch 23&#x20;

Minting process is player-initiated and works in the following way:&#x20;

* At some point in time (t), a player can initiate a Stone Shard mint transaction with attached value of v (in ether, potentially - in LEQ)

**`mint(s, l, v)`**

OR

**`mint(l, v)`**

if the following conditions are satisfied:&#x20;

* \[optional] s >= s\_avail(l) && s in {Sizes}, where s\_avail is current mintable limit at location l, and {Sizes} is a set of priced sizes&#x20;
* l == player.location
* v == mint\_price(s), where mint\_price is a preset price of minting a stone of size s, if the first form is used&#x20;

OR&#x20;

* a constant price of mint of a random stone, if the second form is used
* If the conditions are met and there are no other competing transactions in the block where player’s transaction will be mined, the player is guaranteed to get a Stone at location l of a size s + d, where d is a \[pseudo-]random delta of +/-20% of s&#x20;
* Kind of stone is not guaranteed, and will be assigned \[pseudo-]randomly
