<template>
  <div class="btn" @click="console.log(this.color)">
    <!-- <h3>Tester</h3> -->
  </div>
</template>

<script>
  export default {
    props: {
    color: {
      type: String,
      required: true,
      default: "red",
    },
    },
    data() {
      return {
      }
    },
  }
</script>

<style scoped>
  .btn{
    width: 100px;
    aspect-ratio: 1/1;
    background-color: v-bind(color);
  }
</style>
