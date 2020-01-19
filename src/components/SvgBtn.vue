<template>
    <div class="svg-wrapper" v-on:click="callback(msg)">
      <svg height="60" width="320" xmlns="http://www.w3.org/2000/svg">
        <rect class="shape" height="60" width="320" />
      </svg>
       <span class="text">{{msg}}</span>
    </div>
</template>

<script>
export default {
  name: 'SvgBtn',
  props: {
    msg: String,
    callback: Function
  }
}
</script>

<style scoped>
.shape {
  stroke-dasharray: 140 540;
  stroke-dashoffset: -474;
  stroke-width: 8px;
  fill: transparent;
  stroke: black;
  border-bottom: 5px solid black;
  transition: stroke-width 1s, stroke-dashoffset 1s, stroke-dasharray 1s;
}
.text {
  font-family: 'Roboto Condensed';
  font-size: 22px;
  line-height: 32px;
  letter-spacing: 8px;
  color: black;
  text-transform: uppercase;
  top: -48px;
  position: relative;
}
.svg-wrapper:hover .shape {
  stroke-width: 4px;
  stroke-dashoffset: 0;
  stroke-dasharray: 760;
}
</style>