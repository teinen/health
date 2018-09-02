<template>
  <div>
    <h1>Weight Data Graph</h1>
    <canvas id="myChart"></canvas>
  </div>
</template>

<script>
import jsonData from './data/weight.json'

export default {
  data () {
    return {
      weights: jsonData
    }
  },
  mounted () {
    const ctx = document.getElementById('myChart');
    const myChart = new Chart(ctx, {
      type: 'line',
      data: {
        labels: Object.keys(jsonData),
        datasets: [{
            label: "Weights",
            lineTension: 0.2,
            backgroundColor: 'rgba(255, 99, 132, 0.3)',
            borderColor: 'rgba(255, 99, 132, 1)',
            data: Object.values(jsonData),
        }]
      },
      options: {

      }
    })
  }
}
</script>
