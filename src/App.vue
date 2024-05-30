<template>
  <h1 :class="{appear: toggle}">Ge-mu</h1>
  <button @click="setToggle">Test button</button>
  <br>
  <div id="grid">
    <appBlock v-for="prop_color in colors" :key="prop_color" :id="prop_color" :color='prop_color'/>
  </div>
  <br>
  <button @click="set">Play</button>
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
      toggle: false,
      colors: ['red', 'orange', 'yellow', 'green', 'blue', 'indigo', 'violet', 'black', 'white'],
      temp_colors: [],
      order: [],
      turn: 0,
    }
  },
  created(){
    this.temp_colors = this.colors.slice();
  },
  methods: {
    setToggle(){
      this.toggle = true;
      setTimeout(() => {
        this.toggle = false; 
      }, 100);
    },
    set(){
      this.turn++
      this.order.push(this.temp_colors.pop(Math.floor(Math.random()*this.temp_colors.length)))  
      console.log("turn: " + this.turn)
      let text = ''
      for(let x of this.order) text += x + ' '
      console.log(text)
    }
  },
};

</script>

<style scoped>
  *{margin: 0 !important; }

  .appear{
    animation: show 1s;
  }

  @keyframes show{
    0%{
     opacity: 0;
    }
    100%{
      opacity: 100%;
    }
  }
  #grid{
    display: inline-grid;
    grid-template-columns: auto auto auto;
    background-color: darkseagreen;
    gap: 10px;
    padding: 10px;
  }
</style>
