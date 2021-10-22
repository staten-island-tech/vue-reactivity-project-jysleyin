<template>
  <div id="app">
   <h1>Mama's Sandwicheria</h1>
    <div v-for = "(piece,index) in pieces" v-bind:key="index" @click="addClick()"> <button> {{ piece.name }} </button> </div>
    <div id="food"><img :src= pieces.imgURL></div>
    <img src="./assets/BREAD.png">
  </div>
</template>

<script>


export default {
  name: 'App',
  data () {
  return {
    // selectedPiece: 0,
  pieces: [
    {
    name: "bread",
    id: 1,
    imgURL: require('./assets/BREAD.png'),
    },
    {
    name: "tomato",
    id: 2,
    imgURL: require('./assets/tomato.png')
    },
    {
    name: "meat",
    id: 3,
    imgURL: require('./assets/PATTY.png')
    },
    {
    name: "lettuce",
    id: 4,
    imgURL: require('./assets/LETTUCE.png')
    },
    {
    name: "cheese",
    id: 5,
    imgURL: require('./assets/CHEESE.png')
    },
    {
    name: "sauce",
    id: 6,
    imgURL: require('./assets/SAUCE.png')
    }
  ]

  }
  },
  methods: {
    // updateProduct(index){
    // this.selectedPiece = index;
    // },
    
    addClick: function() {
      
      
    }
  },

  components: {
  }
}

</script>

<style>

body {
background-color: tan;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  list-style-type: none;
  background-color: white;  

}

button {
  font-size: 20px;
}


</style>
