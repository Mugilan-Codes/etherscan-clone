<template>
  <div class="content">
    <h1>Accounts</h1>
    <table>
      <thead>
        <tr>
          <th>#</th>
          <th>Address</th>
          <th>Balance</th>
          <th>Txn Count</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(account, index) in accounts" :key="account.address">
          <td>{{ index + 1 }}</td>
          <td>{{ account.address }}</td>
          <td>{{ account.balance }} Ether</td>
          <td>{{ account.txnCount }}</td>
        </tr>
      </tbody>
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
      accounts.forEach((account) => {
        let newAccount = {
          address: account,
          balance: 0,
          txnCount: 0,
        };

        web3.eth.getBalance(account).then((balance) => {
          newAccount.balance = web3.utils.fromWei(balance, "ether");
        });

        web3.eth.getTransactionCount(account).then((count) => {
          newAccount.txnCount = count;
        });

        this.accounts.push(newAccount);
      });
    });
  },
};
</script>
