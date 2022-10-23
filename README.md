# Introduction

This project was carried out by following the tutorial proposed by buildspace.

Website : https://app.buildspace.so/

Tutorial : " Mint your own NFT collection and ship a Web3 app to show them off"

Each branch represents a step of the tutorial 

1. 

   a. Create a local NFT 

   b. Deploy to network rinkey with alchemy

2. Generate NFT on-chain

3. Use the deployed contract in web app

4. Next step

## Results

Web app made with replit.com : https://replit.com/@rya-sge/nft-starter-project

Link wep app : [https://nft-starter-project.rya-sge.repl.co](https://nft-starter-project.rya-sge.repl.co/)

Last version of the collection available on OpenSea : https://testnets.opensea.io/collection/flowerpower-wu5p8hwnk2

Last contract address : 0x6Cd83F987eEEEc3a917cD80D35265a71F50E5702



# Command

List of hardhat commands 

```shell
npx hardhat accounts
npx hardhat compile
npx hardhat clean
npx hardhat test
npx hardhat node
node scripts/sample-script.js
npx hardhat help
```



## External libraries and tools

### Hardhat

Blockchain-dedicated development environment   Allows you to quickly compile smart contracts. It is possible to deploy them on the blockchain or on a local blockchain for testing. 

Lien : [https://hardhat.org](https://hardhat.org)

### Ethereum-waffle

Allows you to locally compile smart contracts for testing

Lien : [https://www.npmjs.com/package/ethereum-waffle](https://www.npmjs.com/package/ethereum-waffle)

### OpenZeppelin

Use for secure smart contract development.

Link : [https://openzeppelin.com](https://openzeppelin.com)

Lien documentation ERC 721 : [https://docs.openzeppelin.com/contracts/4.x/erc721](https://docs.openzeppelin.com/contracts/4.x/erc721)

Some functions  : 

- [`ERC721URIStorage`](https://docs.openzeppelin.com/contracts/4.x/api/token/erc721#ERC721URIStorage) : contract implementing the ERC721 standard which includes standard metadata extensions  ([`IERC721Metadata`](https://docs.openzeppelin.com/contracts/4.x/api/token/erc721#IERC721Metadata))  
- [`_setTokenURI`](https://docs.openzeppelin.com/contracts/4.x/api/token/erc721#ERC721-_setTokenURI-uint256-string-) : saves metadata in the NFT.
- [`ERC721PresetMinterPauserAutoId`](https://docs.openzeppelin.com/contracts/4.x/erc721#api:presets.adoc#ERC721PresetMinterPauserAutoId). It is preset to allow for token minting (create) with token ID and URI auto generation,
- The `tokenURI` contains the location of the NFT data. This is usually linked to a JSON file called metadata

Example :

```
//Miné le NFT avec comme propriétaire l'adresse de msg.sender et l'id newItemId
_safeMint(msg.sender, newItemId);

 //Mise à jour de l'URI (métadonné du NFT)
 _setTokenURI(newItemId, finalTokenUri);

//Incrémenter l'id du NFT
_tokenIds.increment();
```



### Alchemy

Alchemy facilitates the "broadcast" of the contract created so that it is quickly processed by minors. Once the transaction is mined, the contract will then be "broadcasted" to the rest of the network.

Lien : [https://www.alchemy.com/](https://www.alchemy.com/)

### OpenSea

Platform for trading NFTs. Note: The platform follows the ERC721 standard regarding NFT metadata.

### Ethersv5.4

This library was not used in the project code. It is used on the client side to interact with the user, Metamask and the deployed contract

Link : [ethersv5.4](https://docs.ethers.io/v5/)

Example :

```javascript
   const  CONTRACT_ADDRESS = "0x6Cd83F987eEEEc3a917cD80D35265a71F50E5702"

  try {
    const { ethereum } = window;

    if (ethereum) {
      const provider = new ethers.providers.Web3Provider(ethereum);
      const signer = provider.getSigner();
      const connectedContract = new ethers.Contract(CONTRACT_ADDRESS, myEpicNft.abi, signer);
      }
```

