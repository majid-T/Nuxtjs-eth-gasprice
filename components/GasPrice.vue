<template>
  <div class="price-card">
    <h3>fast : {{ gasPrice.fast }}</h3>
    <h3>fastest: {{ gasPrice.fastest }}</h3>
    <h3>safeLow: {{ gasPrice.safeLow }}</h3>
    <h3>average{{ gasPrice.average }}</h3>
    <h3>block_time: {{ gasPrice.block_time }}</h3>
    <h3>blockNum: {{ gasPrice.blockNum }}</h3>
    <h3>speed: {{ gasPrice.speed }}</h3>
    <h3>safeLowWait: {{ gasPrice.safeLowWait }}</h3>
    <h3>avgWait: {{ gasPrice.avgWait }}</h3>
    <h3>fastWait {{ gasPrice.fastWait }}</h3>
    <h3>fastestWait {{ gasPrice.fastestWait }}</h3>
  </div>
</template>

<script>
export default {
  name: "GasPrice",
  props: ["gasPrice"]
};
</script>

<style>
.price-card {
  padding: 1rem;
  border: 1px dotted #ccc;
  margin: 1rem 0;
}
</style>
