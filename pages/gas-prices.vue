<template>
  <div class="container">
    <h2>Gas Prices Page</h2>
    <h3>fast : {{ gasPrices.fast }}</h3>
    <h3>fastest: {{ gasPrices.fastest }}</h3>
    <h3>safeLow: {{ gasPrices.safeLow }}</h3>
    <h3>average{{ gasPrices.average }}</h3>
    <h3>block_time: {{ gasPrices.block_time }}</h3>
    <h3>blockNum: {{ gasPrices.blockNum }}</h3>
    <h3>speed: {{ gasPrices.speed }}</h3>
    <h3>safeLowWait: {{ gasPrices.safeLowWait }}</h3>
    <h3>avgWait: {{ gasPrices.avgWait }}</h3>
    <h3>fastWait {{ gasPrices.fastWait }}</h3>
    <h3>fastestWait {{ gasPrices.fastestWait }}</h3>
  </div>
</template>

<script>
import axios from "axios";
let key;
export default {
  async asyncData({ $config: { apiSecret, url } }) {
    try {
      const result = await axios.get(url + apiSecret);
      return { gasPrices: result.data };
    } catch (err) {
      console.log(err);
    }
  },
  head() {
    return {
      title: "Gas Prices",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Get latest ethereum gas price from here",
        },
      ],
    };
  },
};
</script>

<style></style>
