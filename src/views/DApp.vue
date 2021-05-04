<template>
  <div class="content">
    <form class="box">
      <div class="label">Current Value: {{ value }}</div>
      <div class="field">
        <label class="label">Enter a number:</label>
        <div class="control">
          <input type="text" v-model="newValue" class="input" />
        </div>
      </div>
      <button @click="storeNumber()" class="button is-primary">Store</button>
    </form>
  </div>
</template>

<script>
let Web3 = require("web3");
let web3 = new Web3("http://localhost:7545");

// get from ganache (created contact address in transactions)
let contractAddress = "0x5F792B3d0659baC6742213edDb10517133DBb905";

// Get from remix ide (artifacts --> [contract]_metadata.json --> output --> abi)
let contractABI = [
  {
    inputs: [],
    name: "retrieve",
    outputs: [
      {
        internalType: "uint256",
        name: "",
        type: "uint256",
      },
    ],
    stateMutability: "view",
    type: "function",
  },
  {
    inputs: [
      {
        internalType: "uint256",
        name: "num",
        type: "uint256",
      },
    ],
    name: "store",
    outputs: [],
    stateMutability: "nonpayable",
    type: "function",
  },
];

let storage = new web3.eth.Contract(contractABI, contractAddress);
export default {
  data() {
    return {
      value: 0,
      newValue: 0,
    };
  },
  methods: {
    storeNumber() {
      storage.methods
        .store(this.newValue)
        .send({ from: "0xA6aAaFd31388EFDc2E202e52D6F004F8ba53eF20" })
        .then((response) => {
          console.log("storeNumber response =", response);
          this.getNumber();
        });
    },
    getNumber() {
      storage.methods
        .retrieve()
        .call()
        .then((response) => {
          this.value = response;
        });
    },
  },
  mounted() {
    this.getNumber();
  },
};
</script>
