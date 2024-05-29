<template>
  <h1>Ge-mu</h1>
  <div id="grid">
    <appBlock v-for="prop_color in colors" :key="prop_color" :color='prop_color'/>
  </div>
  <br>
  <button @click="pop">Play</button>
</template>
<script>
import appBlock from './components/appBlock.vue'
export default {
  name: 'App',
  components: {
    appBlock,
  },
  data() {
    return {
      colors: ['red', 'orange', 'yellow', 'green', 'blue', 'indigo', 'violet', 'black', 'white'],
      temp_colors: [],
      turn: 0,
    }
  },
  created(){
    this.temp_colors = this.colors.slice();
  },
  methods: {
    pop(){
      console.log(this.colors)
      console.log(this.temp_colors)
      this.temp_colors.pop()
    }
  },
};

</script>

<style scoped>
  *{margin: 0 !important; }
  #grid{
    display: inline-grid;
    grid-template-columns: auto auto auto;
    background-color: darkseagreen;
    gap: 10px;
    padding: 10px;
  }
</style>
