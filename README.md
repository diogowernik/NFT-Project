# `ethereum-NFT-Marketplace`

#  `UI-UX`:
- Press on mint button on the website
- Connect wallet
- Examine if wallet is on white list
- If yes, allow mint of up to 5 NFTs (if stage 1, if stage 2 up to 3, if stage 3, up to 2)
- If mint, transfer a random NFT picture from 0x000 wallet of the smart contract to wallet of minter.
- Update white list, that wallet has minted x amount of NFTs.

# `Smart-Contract`

- Name: SuperCarClub Lamborghini Edition
- 8888 NFTs
- every buyer gets the ownership over 1 NFT picture
- 3 Sale Stages:
o 1. Stage 1000 NFT price: 0.08 ETH per NFT
  ROYALTIES 10%
  Whitelist of 1000 people who can mint. Whitelist contains wallets. Should con
  Can mint up to 5 per wallet
o 2. Stage 3444 NFT price: 0.15 ETH per NFT
  Can mint up to 3 per wallet
o 3. Stage 4444 NFT price: 0.23 ETH per NFT
  Can mint up to 2 per wallet
- Switch from stage to stage is manual, done by us (holder of a wallet, or software developer) or when the number of mintable NFTs in that stage ends (stage 1 after 1000 are minted).
- exclusive access to Video game - connected to the purchase of one NFT – the buyer of an NFT receives a number/code for exclusive access.
- exclusive access to a website only for NFT holders.
- Should be done via a custom erc721 contract https://www.erc721a.org
- ERC721A github for the contract: https://github.com/chiru-labs/ERC721A


.env

```jsx
REACT_APP_MORALIS_APPLICATION_ID = xxxxxxxxxxxx
REACT_APP_MORALIS_SERVER_URL = https://xxxxxx.grandmoralis.com:2053/server
```

🔎 Locate the MoralisDappProvider in `src/providers/MoralisDappProvider/MoralisDappProvider.js` and paste the deployed marketplace smart contract address and ABI
```jsx
const [contractABI, setContractABI] = useState();
const [marketAddress, setMarketAddress] = useState();
```

🔃 Sync the `MarketItemCreated` event `/src/contracts/marketplaceBoilerplate.sol` contract with your Moralis Server, making the tableName `MarketItems`
```jsx
event MarketItemCreated (
  uint indexed itemId,
  address indexed nftContract,
  uint256 indexed tokenId,
  address seller,
  address owner,
  uint256 price,
  bool sold
);
```


🚴‍♂️ Run your App:
```sh
yarn start
```


