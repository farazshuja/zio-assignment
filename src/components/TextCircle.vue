<template>
  <g>
    <circle
      ref="circle"
      :cx="data.cx"
      :cy="data.cy"
      :r="width"
      :fill="data.fill"></circle>
    <text
      ref="text"
      :x="data.cx"
      :y="data.cy">
        {{text}}
    </text>
  </g>
</template>

<script>
/**
 * Require properties are text and data
 * data is of the following structure
 *  cx - center-x of the circle
 *  cy - center-y of the circle
 *  r - radius of the circle
 *  fill - fill color of the circle
 */
export default {
  props: ['text', 'data'],
  data () {
    return {
      width: this.data.r
    }
  },
  updated () {
    // adjust text length if its getting closer to the width of circle
    const circleWidth = this.$refs.circle.getBBox().width
    const textWidth = this.$refs.text.getBBox().width

    // if its getting closer to margin of 10
    if (textWidth >= (circleWidth - 10)) {
      this.width = textWidth / 1.7  // const factor to cover the margin
    } else if (textWidth <= (this.data.r * 1.7)) {
      this.width = this.data.r
    }    

  }
}
</script>


<style scoped>
  circle {
    stroke: #444;
    stroke-width: 1px;
  }
  text {
    text-anchor: middle;
    font-family: 'Helvetica';
    font-size: 12px;
  }
</style>

