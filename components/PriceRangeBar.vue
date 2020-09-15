<template>
  <div class="bar-chart">
    <bar-chart :data="barChartData" :options="barChartOptions" :height="200" />
    {{ ranges }}
  </div>
</template>

<script>
export default {
  name: "PriceRangeBar",
  props: ["ranges"],
  data() {
    return {
      barChartData: {
        labels: Object.keys(this.ranges),
        datasets: [
          {
            label: "Price",
            data: Object.values(this.ranges),
            backgroundColor: "#003f5c"
          }
        ]
      },
      barChartOptions: {
        responsive: true,
        legend: {
          display: false
        },
        title: {
          display: true,
          text: "Gas Price Ranges",
          fontSize: 24,
          fontColor: "#6b7280"
        },
        tooltips: {
          backgroundColor: "#17BF62"
        },
        scales: {
          xAxes: [
            {
              gridLines: {
                display: false
              }
            }
          ],
          yAxes: [
            {
              ticks: {
                beginAtZero: false
              },
              gridLines: {
                display: false
              }
            }
          ]
        }
      }
    };
  }
};
</script>

<style></style>
