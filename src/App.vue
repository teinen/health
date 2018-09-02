<template>
  <div>
    <h1>Weight Data Graph</h1>
    <div>
      <p v-for="(value, key) in weights" :key="key">{{ key }}: {{ value }}</p>
    </div>
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
}
</script>
