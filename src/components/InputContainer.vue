<template>
  <div class="container">
    <input v-model="text" type="text" />
    <svg id="text-circles-svg" width="100%" height="300">
      <text-circle v-for="(circle, index) in circles"
        :key="index"
        :text="text"
        :data="circle">
      </text-circle>
    </svg>
  </div>
</template>

<script>
import TextCircle from './TextCircle'

export default {
  components: {
    TextCircle
  },
  data () {
    return {
      text: '',
      circles: [
        {
          cx: 200,
          cy: 50,
          r: 40,
          fill: '#cfe2f3'
        },
        {
          cx: 200,
          cy: 200,
          r: 80,
          fill: '#cfe2f3'
        }
      ]
    }
  }
}
</script>

