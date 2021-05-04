# etherscan-clone

## A [Etherscan](https://etherscan.io/) Clone using Vue CLI and Web3.js

### How to run

- Using geth
  - Initialize the Network using genesis.json file in a separate folder

      ```sh
      geth --rpc --rpcport "8545" --datadir ./chaindata init ./genesis.json
      ```

  - Start the network with a single ethereum node

    ```sh
    geth --rpc --rpcport "8545" --datadir ./chaindata --rpcapi admin,eth,net,web3,personal,miner,txpool --rpccorsdomain "*" --allow-insecure-unlock
    ```

- Using Ganache
  - Create a blockchain
  - Deploy the contract using Remix IDE with web3 provider as environment pointing to Ganache RPC
  - go to the [contract]_metadata.json and get the abi (Application Binary) array
  - The abi is use to create web apps and to use the functions defined in the contracts

### Scripts (package.json)

- Install Packages

```sh
npm install
```

- Compiles and hot-reloads for development

```sh
npm run serve
```

- Compiles and minifies for production

```sh
npm run build
```

- Lints and fixes files

```sh
npm run lint
```

### DOCS

- [Vue CLI](https://cli.vuejs.org/)
  - [Customize configuration](https://cli.vuejs.org/config/).
- [Vue.js v2](https://vuejs.org/v2/guide/)
- [web3.js - Ethereum JavaScript API](https://web3js.readthedocs.io/en/v1.3.4/)
  - [utils - fromWei](https://web3js.readthedocs.io/en/v1.3.4/web3-utils.html#fromwei)
- [Vetur - Vue tooling for VS Code](https://vuejs.github.io/vetur/)
  - [Setup](https://vuejs.github.io/vetur/guide/setup.html)
  - [vetur.config.js](https://vuejs.github.io/vetur/guide/setup.html#advanced)
- [Vue Router](https://router.vuejs.org/)
  - [Install using Vue-Cli](https://router.vuejs.org/installation.html#vue-cli)
- [Bulma CSS Framework](https://bulma.io/)
  - [GitHub](https://github.com/jgthms/bulma)
  - [Usage](https://github.com/neovive/bulma-vuecli/blob/master/README.md)
  - [CSS Import Rule](https://www.w3schools.com/cssref/pr_import_rule.asp)
- [Ganache - Geth Alternative](https://www.trufflesuite.com/ganache)
- [Remix IDE](https://remix.ethereum.org/)

#### Other Articles

- [Quick VSCode setup for Vue.js with Prettier and ESLint](https://mattgosden.medium.com/quick-vscode-setup-for-vue-js-with-prettier-and-eslint-4b97fc71c587)
- [Formatting Vue.js Code with ESLint & Prettier](https://www.digitalocean.com/community/tutorials/vuejs-vue-eslint-prettier)
