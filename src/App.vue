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
      periods: this.getPeriods(),
      weights: this.getEachPeriodData()
    }
  },
  methods: {
    getPeriods (json) {
      let keys = Object.keys(jsonData)
      keys = keys.map(value => value.substr(0, 7))
      return keys.filter((x, i, self) => self.indexOf(x) === i)
    },
    getEachPeriodData() {
      
    }
  },
  mounted () {
    const ctx = document.getElementById('myChart');
    const myChart = new Chart(ctx, {
      type: 'line',
      data: {
        // labels: ['2018-01-01', '2018-01-02','2018-01-03','2018-01-04','2018-01-05'],
        labels: Object.keys(jsonData),
        datasets: [{
            label: "Weights",
            lineTension: 0.2,
            backgroundColor: 'rgba(255, 99, 132, 0.3)',
            borderColor: 'rgba(255, 99, 132, 1)',
            // data: ['80.0', '79.5', '81.0', '81.5', '80.0'],
            data: Object.values(jsonData)
        }]
      },
      options: {
        scales: {
          yAxes: [{
            id: "y-axis",
            type: "linear",
            position: "left",
            ticks: {
                max: 85.0,
                min: 75.0,
                stepSize: 1.0
            },
          }]
        }
      }
    })
  }
}
</script>
