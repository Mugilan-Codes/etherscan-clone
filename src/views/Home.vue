<template>
  <div class="content">
    <h1>Accounts</h1>
    <table>
      <tr v-for="account in accounts" :key="account">
        <td>{{ account }}</td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      accounts: [],
    };
  },
  mounted() {
    let Web3 = require("web3");
    let web3 = new Web3("http://localhost:8545");
    web3.eth.getAccounts().then((accounts) => {
      this.accounts = accounts;
    });
  },
};
</script>
