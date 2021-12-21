# Game Architecture

![](https://lh3.googleusercontent.com/GHgaJudUt4gkt3QdWFqHhY5fkmhXMeB1-BzT8tKGt0VIXpFXfPn4LX68aK-vPmxqNGl7LoneUwjQI9BhM3O6\_BLjeCo6az0OXRIywGdwz1jEffLa\_czMoRde\_wH\_uep5JQxSCT0D)

One of the unique features of the Keepers of the Cryptoverse is its modular design.&#x20;

The Game is comprised of several types of smart contracts that are interlinked with a standardized interface (Game Item):&#x20;

* **Game Master**: main entrypoint for all external transactions, which features the common interface and common part of the game logic,&#x20;
* **Players**: ERC721-based contract that keeps track of players and their state (lifetime, progress, level, achievements (badges), avatar/skin, etc.),&#x20;
* **Recipes**: Collection of game logic concerning possible combinations (fusions, chemistry, alchemy) of various game items. Could be represented by one or more smart contracts and upgrade in the future&#x20;
* **Game Items**: Either ERC721 or ERC1155 compatible contracts for keeping state of specific items and item-specific game logic.&#x20;

Such modular architecture has several big advantages:&#x20;

* Allows for modular expansion and upgradability of components one by one,&#x20;
* Allows for quick and efficient fault isolation (in case a bug is discovered in code of one of the contracts),&#x20;
* Allows to avoid contract code bloat and limitations of squeezing all logic into a single contract
