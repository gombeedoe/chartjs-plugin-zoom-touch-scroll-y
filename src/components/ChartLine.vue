<template>
  <canvas ref="myChart" height="600" />
</template>

<script>
import { Chart, registerables } from "chart.js";
import zoomPlugin from "chartjs-plugin-zoom";

export default {
  data() {
    return {
      chartInstance: null,
    };
  },
  mounted() {
    Chart.register(...registerables, zoomPlugin);
    let ctx = this.$refs.myChart.getContext("2d");
    this.chartInstance = new Chart(ctx, {
      type: "line",
      data: {
        labels: [
          "January",
          "February",
          "March",
          "April",
          "May",
          "June",
          "July",
          "August",
          "September",
          "October",
          "November",
          "December",
        ],
        datasets: [
          {
            data: [11, 81, 91, 46, 91, 18, 23, 96, 98, 32, 90, 76],
          },
        ],
      },
      options: {
        responsive: true,
        maintainAspectRatio: false,
        scales: {
          x: {
            max: 4,
            position: "bottom",
            ticks: {
              align: "center",
              autoSkip: false,
            },
          },
          y: {
            suggestedMax: 100,
            position: "left",
            beginAtZero: true,
          },
        },
        plugins: {
          zoom: {
            pan: {
              enabled: true,
              mode: "x",
            },
          },
        },
      },
    });
    this.chartInstance.canvas.style.touchAction = "pan-y";
  },
};
</script>
