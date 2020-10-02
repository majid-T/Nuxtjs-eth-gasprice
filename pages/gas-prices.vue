<template>
  <div>
    <div v-if="!isLoading" class="container">
      <h2>Gas Prices Page</h2>
      <GasPrice :gasPrice="gasPrice" />
      <PriceRangeBar :ranges="gasPrice.gasPriceRange" />
    </div>
    <b-loading v-else :is-full-page="true" v-model="isLoading"></b-loading>
  </div>
</template>

<script>
import axios from "axios";
import GasPrice from "../components/GasPrice";
import PriceRangeBar from "../components/PriceRangeBar";

export default {
  data() {
    return {
      isLoading: true,
    };
  },
  async asyncData({ $config: { apiSecret, url } }) {
    try {
      const result = await axios.get(url + apiSecret);

      return { gasPrice: result.data };
    } catch (err) {
      console.log(err);
    }
  },
  components: {
    GasPrice,
    PriceRangeBar,
  },
  mounted() {
    this.isLoading = false;
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
