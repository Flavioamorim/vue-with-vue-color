<template>
  <div id="app">
    <img src="./assets/logo.png">
    <hello></hello>
    <color></color>

    <!-- <photoshop-picker v-model="colors" @change-color="onChange"></photoshop-picker> -->
    <compact-picker v-model="colors" @change-color="onChange"></compact-picker>


  </div>
  </div>
</template>

<script>
import Hello from './components/Hello'
import Color from './components/Color'
import { Photoshop  }  from 'vue-color'
import { Compact  }  from 'vue-color'
import $ from "jquery";



var defaultProps = {
  hex: '#194d33',
  hsl: {
    h: 150,
    s: 0.5,
    l: 0.2,
    a: 1
  },
  hsv: {
    h: 150,
    s: 0.66,
    v: 0.30,
    a: 1
  },
  rgba: {
    r: 25,
    g: 77,
    b: 51,
    a: 1
  },
  a: 1
}


export default {
  name: 'app',
  components: {
    Hello,
    Color,
    'photoshop-picker': Photoshop,
    'compact-picker': Compact,

  },
  created(){
    $(document).ready(function($) {

        console.log('jqyer')
    });
  },
  data(){
    return { colors: defaultProps }
  },
  methods:{
    onChange (val) {
      console.log(val)
      this.colors = val
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
