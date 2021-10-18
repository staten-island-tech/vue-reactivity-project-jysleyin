<template>
  <div id="app">
   <h1>Mama's Sandwicheria</h1>
    <li v-for = "piece in pieces" :key="piece"> <button> {{ piece }} </button> </li>
  </div>
</template>

<script>


export default {
  name: 'App',
  data () {
  return {
  pieces: [
    "bread",
    "tomato",
    "meat",
    "lettuce"
  ]

  }
  },
  components: {
  }
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  list-style-type: none;
}
</style>
