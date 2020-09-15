<template>
  <div class="container">
    <h2>Gas Prices Page</h2>
    <GasPrice :gasPrice="gasPrice" />
  </div>
</template>

<script>
import axios from "axios";
import GasPrice from "../components/GasPrice";

export default {
  async asyncData({ $config: { apiSecret, url } }) {
    try {
      const result = await axios.get(url + apiSecret);
      return { gasPrice: result.data };
    } catch (err) {
      console.log(err);
    }
  },
  components: {
    GasPrice
  },
  head() {
    return {
      title: "Gas Prices",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Get latest ethereum gas price from here"
        }
      ]
    };
  }
};
</script>

<style></style>
