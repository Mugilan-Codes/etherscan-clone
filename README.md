# etherscan-clone

## A [Etherscan](https://etherscan.io/) Clone using Vue CLI and Web3.js

### How to run

- Initialize the Network using genesis.json file in a separate folder

    ```sh
    geth --rpc --rpcport "8545" --datadir ./chaindata init ./genesis.json
    ```

- Start the network with a single ethereum node

  ```sh
  geth --rpc --rpcport "8545" --datadir ./chaindata --rpcapi admin,eth,net,web3,personal,miner,txpool --rpccorsdomain "*" --allow-insecure-unlock
  ```

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
- [Vetur - Vue tooling for VS Code](https://vuejs.github.io/vetur/)
  - [Setup](https://vuejs.github.io/vetur/guide/setup.html)
  - [vetur.config.js](https://vuejs.github.io/vetur/guide/setup.html#advanced)

#### Other Articles

- [Quick VSCode setup for Vue.js with Prettier and ESLint](https://mattgosden.medium.com/quick-vscode-setup-for-vue-js-with-prettier-and-eslint-4b97fc71c587)
- [Formatting Vue.js Code with ESLint & Prettier](https://www.digitalocean.com/community/tutorials/vuejs-vue-eslint-prettier)
