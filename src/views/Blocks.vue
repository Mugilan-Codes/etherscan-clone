<template>
  <div class="content">
    <h1>Blocks (Total of {{ blockNumber }} blocks)</h1>
    <table class="table is-bordered">
      <thead>
        <tr>
          <th>Block Number</th>
          <th>Hash</th>
          <th>Gas Used</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="block in blocks" :key="block.hash">
          <td>{{ block.number }}</td>
          <td>{{ block.hash }}</td>
          <td>{{ block.gasUsed }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      blocks: [],
      blockNumber: 0,
    };
  },
  async mounted() {
    let Web3 = require("web3");
    let web3 = new Web3("http://localhost:8545");

    this.blockNumber = await web3.eth.getBlockNumber();

    for (let i = 0; i < 10; i++) {
      web3.eth.getBlock(this.blockNumber - i).then((block) => {
        this.blocks.push(block);
      });
    }
  },
};
</script>