<template>
  <div id="app">
    EtherScan App
    <table>
      <tr v-for="account in accounts" :key="account">
        <td>{{ account }}</td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      accounts: [],
    };
  },
  mounted() {
    let Web3 = require("web3");
    let web3 = new Web3("http://localhost:8545");
    let self = this;
    web3.eth.getAccounts().then((accounts) => {
      self.accounts = accounts;
    });
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>