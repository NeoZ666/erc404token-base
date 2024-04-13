# ERC404 Concept Project

This project demonstrates usage of ERC404 and DN404 token, which are a combination of ERC20 and ERC721 token implementation. DN404 is built on top of ERC404 with two base contract implementation instead of one for ERC404. 

- Run the following command to install the dependencies:

  ```shell
  npm install dotenv --save --force
  npm install --save-dev hardhat --force
  npm install --force
  ```

- Try running some of the following tasks to test your project:
  
  ```shell
  npx hardhat help
  npx hardhat test
  REPORT_GAS=true npx hardhat test
  npx hardhat node
  npx hardhat run scripts/deploy.js
  ```

- Use your Infura Key in `hardhat.config.js` file to configure the network to use. Here, we are testing using Polygon Mumbai / Amoy / Sepolia :
  
  ```shell
      mumbai: {
        url: "https://rpc.ankr.com/polygon_mumbai",
        accounts: privateKey(),
      },
      sepolia: {
        url: "https://sepolia.infura.io/v3/558d4274c7d14050a32b0a4dab8e3a7a",
        accounts: privateKey(),
      }
  ```

- Now, compile and deploy the contract using Hardhat :
  
  ```shell
  npx hardhat compile
  ```
  
- Deploy on aforementioned Network(we are using Sepolia or Polygon) here :
  
  ```shell
  npx hardhat run scripts/deployToken.js --network sepolia
  npx hardhat run scripts/deployMarketplace.js --network sepolia
  ```

- This should give 2 contract addresses, navigate to `.\frontend\src\components\ConnectWallet.js` and replace :
  ```shell
    const marketplaceAddress = "YOUR_MARKETPLACEADDRESS_HERE";
    const nftContractAddress = "YOUR_NFTCONTRACTADDRESS_HERE";
  ```

- Copy the .json contractABIs of deployed contracts from `.\contracts\Interface\IDN404.json` and `.\contracts\lib` to `.\frontend\src\` 

- Now navigate to `.\frontend\` in terminal and run the following command to install frontend dependencies:
  
  ```shell
  npm install --force
  ```

  - Ignore all warnings.
