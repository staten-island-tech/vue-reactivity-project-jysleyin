<template>
  <div name="app">
   <h1>Mama's Sandwicheria</h1>
    <li v-for = "(piece,index) in pieces" v-bind:key="piece.id" @click="addClick()"> <button> {{ piece.name }} </button> </li>
    <div class="list"></div>
    <img src="./assets/BREAD.png">
  </div>
</template>

<script>


export default {
  name: 'App',
  data () {
  return {
    selectedPiece: 0,
  pieces: [
    {
    name: "bread",
    id: 1,
    },
    {
    name: "tomato",
    id: 2,
    },
    {
    name: "meat",
    id: 3,
    },
    {
    name: "lettuce",
    id: 4,
    },
    {
    name: "cheese",
    id: 5,
    },
    {
    name: "sauce",
    id: 6
    }
  ]

  }
  },
  methods: {
    updateProduct(index){
    this.selectedPiece = index;
    },
    addClick: function() {
      alert('filler')
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
