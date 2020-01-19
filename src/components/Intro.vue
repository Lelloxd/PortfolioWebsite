<template>
<div class="intro">
  <div class="intro-work" v-bind:class="{ active: selected === 'SHOW WORK', fadeout: selected === 'SHOW MX'}" :style="{'background-image': `url(${require('../assets/maxresdefault.jpg')})`}">
    <SvgBtn msg="SHOW WORK" class="btn-intro" :callback="setSelected" v-show="selected!=='SHOW WORK'"></SvgBtn>
  </div>
  <div class="intro-mx" v-bind:class="{ active: selected === 'SHOW MX', fadeout: selected === 'SHOW WORK'}" :style="{'background-image': `url(${require('../assets/HSM-blog-pic.jpeg')})`}">
    <SvgBtn msg="SHOW MX" class="btn-intro" :callback="setSelected" v-show="selected!=='SHOW MX'"></SvgBtn>
  </div>
  <SvgBtn msg="BACK" class="btn-back" v-show="selected != false" :callback="() => selected = false"></SvgBtn>
</div>
</template>

<script>
import SvgBtn from './SvgBtn'

export default {
  name: 'Intro',
  props: {
    msg: String
  },
  data: () => {
    return {
      selected: false
    }
  },
  methods: {
    setSelected (value) {
      this.selected = value;
    }
  },
  components: {
    SvgBtn
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.intro-work {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 1;
  height: 100vh;
  transition: width 0.5s, background-size 1s;
  background-repeat: no-repeat;
  background-size: 100% 100%;
  background-position-x: 0;
}
.intro-mx {
  position: absolute;
  top: 0;
  right: 0;
  z-index: 2;
  width: 50vw;
  height: 100vh;
  background: white;
  transition: width 0.5s, background-size 1s;
  background-repeat: no-repeat;
  background-size: 200% 100%;
  background-position-x: 100%;
}

.intro-work.active, .intro-mx.active {
  width: 100%;
  background-size: 100% 100%;
}
.intro-work.fadeout, .intro-mx.fadeout{
  width: 0;
  background-size: 20% 100%;
}
.btn-intro {
  position: relative;
  top: 80%;
  transform: translateY(-50%);
	margin: 0 auto;
  width: 320px;  
}
.intro-work .btn-intro {
  left: 25%;
  margin-left: -160px;
}
.btn-back {
  position: absolute;
  top:20px;
  right: 20px;
  z-index: 3;
}
.intro-mx:focus .intro-work {
  display: none;
}
</style>

<style>
.btn-back .text {
  top: -25px;
  left: -200px;
}
</style>
