# Stone Shards

Stones represent 5 foundational elements of the Cryptoverse:&#x20;

* ![](https://lh4.googleusercontent.com/qNeX-fTZiaN8367\_sbE34VZPgn6sGqTKWxMn1Xzbdtf\_D5FtP\_TxKTdx8rTnTcwJVaqUt98yd9kSuvfGvSyu0zUqJttO-mCyqn22l8DNB9mJRwufVf2oIChHaFzRNAUn6CqWMnXp) **Energy**. This stone is in charge of the circulation of energy in the Cryptoverse. It can also (under certain circumstances) open portals and wormholes&#x20;
* ![](https://lh5.googleusercontent.com/eSJtYm2XQEwW7R6Q2DU6hzR9l9JACBQo0mAOGAk6idshhflTMUPkHfYA8y-3NqQJa2rc43CotV3KZbgpD0RlCrC7kiRIvGzrRQl3qmJvL4VOqrXnBh-BDDDAvNUntuPVBo5N9Vdr) **Matter**. This stone is in charge of creation and transformation of all kinds of matter. Different forms of matter could be combined together and with the help of Dark Energy can create new types&#x20;
* ![](https://lh6.googleusercontent.com/yL-Hk2pYe1hF\_lpE9bDBCeD\_dEoYCmyKVKxsGKq4uk-xcHBNg2Oei4J196PMd8dS8aC4T21A3mAROvZ2Qe9qcOdXrxWLqDPWIm6ixASqMFcNrEfbYHl1SLAWQgHe8cdBtwFFHbSU) **Time**. This stone is responsible for sequential time flow. Certain manipulation can cause time travel / time loops&#x20;
* ![](https://lh5.googleusercontent.com/\_GlSsaQA1MiAIn9p6vqF5ZRJa8W-ZFlysR07OVNVdk\_r2dFoB-Us-EdvMhQ9oGPKiT-wlTZsLJLkcTEJlU-H-7Fu9KwxpCvY2wH6x8S21WVvQYk3azqsYtG-mvBHSrIHCJHV3UuN) **Life**. This stone is responsible for support of various life forms, and also for the creation of new ones&#x20;
* ![](https://lh3.googleusercontent.com/PG\_JZu86uuiSaTQRuoJLw3vUcoBUOilEQv2jmuUWKZZQL6yqhwDDJongjGSb6nWR5hfVM4KsDlRKZkBnZDoEtei3QgeIDU8u7NydJiwxxQjblSmjJFRTH7zOfgPmZQfQTVq6Mfx6) **Mind**. This stone is responsible for maintaining intellect across species of the Cryptoverse&#x20;

Due to the Epic Blast (see [storyline.md](../storyline.md "mention")), all 5 whole foundational Stones have been blown to pieces (Shards) of different sizes, which are now scattered across the Cryptoverse. Since the Shards represent fractions of the whole original foundational Stones, their supply is naturally scarce.

Players’ ability to mine new Stone Shards will be gradually decreasing over time, as more and more Shards get mined.

Stone Shards have the following natural properties:

* **Kind** (corresponds to the kind of original Stone; different kinds of Stones have different properties, which will be revealed at later stages of the Game),&#x20;
* **Size** (is upper-limited by the size of original Stones; determines LEQ emission rate from the locked Stone Shard)

From the crypto design standpoint, properties of Stone Shards qualify them as semi-fungible tokens, represented by ERC-1155 standard. Semi-fungibility means that they are fungible (interchangeable) within a certain kind (i.e. one Energy Stone Shard of size 10 is totally equivalent and undistingushable with another Energy Stone Shard of size 10, etc.) and are non-fungible across different kinds (i.e. one Energy Stone Shard of size 10 is completely different and NOT interchangeable with Matter Stone Shard of size 10, etc.)

### Using Stone Shards

A Shard, being placed inside a Tesseract, gets the ability to emit Light Energy Quanta (LEQ), the in-game utility token.

Multiple Shards of the same kind could be melted together inside a Tesseract to create a bigger, more powerful Stone Shards. Bigger Shards have disproportionately higher LEQ emission rate and vice versa.

### Mining Stone Shards

Stone Shards are finite in their total quantity; combined size of all Stone Shards of any kind can never be bigger than the size of the original foundational Stone.

Stone Shards are mined across the Realms of the Cryptoverse. Originally the Game starts in one central Realm, so potentially mineable amount (total size) of Shards is \~1/5 of the whole amount.

Details of Stone Shards mining over time can be found in section [stone-shards-mining.md](../../tokenomics/stone-shards-mining.md "mention").

Durining initial phase of the Game, due to nature of the Stone Shards supply distribution, it is believed that their supply will be greater than demand, so mining of Stone Shards will be available for all takers (subject to programmed supply constraints).

As the Game progresses and more and more Stone Shards get mined and locked in Tesseracts, at some point demand for the Stone Shards will become greater than supply. At that point the Game will introduce a demand-supply leveling mechanics, such as lotteries or proof-of-X-type competitions.

### Mining and On-Chain Randomness

Since mining of all Stone Shards (exept the ones generated in Genesis mint and distributed via Launch pre-sale) will take place on-chain, the question of enabling sufficient randomness needs to be addressed.

Since EVM state machine is purely deterministic, general consensus is that there is no reliable randomness on-chain. Two solutions for this challenge are proposed:

* Using external Oracles (such as ChainLink VRF),
* Using hashes of future blocks (as described [here](https://medium.com/@soliditydeveloper.com/random-number-generation-for-solidity-smart-contracts-1-9ccfc7fcadf0)).

Since every ChainLink VRF request has distinct cost, we've decided to use the second approach with hashes of future blocks. In a nutshell, hash of every next block on Ethereum network could be deemed as random, provided that risk of miner's manipulation is excluded. The mitigation approach is two-phased:

* In the first phase player pays for the mine operation and the future block number (e.g. current block number + 2) is committed
* Once the future block number is mined, the player can perform the second phase transaction, actually using hash of already mined block to mint new game item (Stone Shard). The only constraint for this phase is that it should be performed within 256 block times (currently a little over 1 hour) since the target block is mined.

The process is illustrated on the diagram below:

![Enabling on-chain randomness](<../../.gitbook/assets/image (1).png>)

