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
      data: this.weights,
    })
  }
}
</script>
