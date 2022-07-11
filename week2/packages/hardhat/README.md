# BuyMeACoffee solidity contract

This repo contains a contract that implements tipping functionality.

Install dependencies with `npm install`.

Set up by creating a `.env` file, and filling out these variables:

```
GOERLI_URL="your Alchemy RPC URL"
GOERLI_API_KEY="your Alchemy API key"
PRIVATE_KEY="your wallet private key"
```

You can get an Alchemy RPC URL for free [here](https://alchemy.com/?a=roadtoweb3weektwo).

Deploy your contract with:

```
npx hardhat run scripts/deploy.js
```

To deploy your contract to a specific network, you need to use the following command:

```
npx hardhat run scripts/deploy.js --network goerli
```

Take into account that the network have to be configured in the file ***hardhat.config.js***

```
module.exports = {
  ...
  networks: {
    goerli: {
      url: GOERLI_URL,
      accounts: [PRIVATE_KEY]
    }
  }
  ...
}
```

Run an example buy coffee flow locally with:

```
npx hardhat run scripts/buy-coffee.js
```

Once you have a contract deployed to Goerli testnet, grab the contract address and update the `contractAddress` variable in `scripts/withdraw.js`, then:

```
npx hardhat run scripts/withdraw.js
```

will allow you to withdraw any tips stored on the contract.
