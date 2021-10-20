<template>
  <div id="app">
   <h1>Mama's Sandwicheria</h1>
    <li v-for = "piece in pieces" :key="piece" @click="addClick()"> <button> {{ piece }} </button> </li>
    <div class="list"></div>
    <img src="./assets/BREAD.png">
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
    "lettuce",
    "cheese",
    "sauce"
  ]

  }
  },
  methods: {
    addClick: function(list) {
      list.style.display = "block";
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

.list {
    display: none;
}
</style>
