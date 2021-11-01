<template>
  <div id="app">
   <h1>Mama's Sandwicheria</h1>
    <div id="sandwich" v-for = "(piece, index) in pieces" v-bind:key="piece.id" >
       <button @click="addClick(index)"> {{ piece.name }} </button> 
    </div>

    <img class="sandwich-image" v-for = "piece in sandwich" :key="piece.id" :src = "piece.imgURL"/>
  </div>
</template>

<script>



export default {
  name: 'App',
  data () {
  return {
    // image: image,
    selectedImage: 0,
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
  ],

  sandwich: [],

  }
  },
  methods: {

    addClick(index){
     this.selectedImage = index;
     console.log(index)
     this.sandwich.push(this.pieces[index])
     console.log(this.sandwich)
    //  document.querySelectorAll(".sandwich-image").style.transform = translateY(5);
    }

  },

  components: {

  },
  computed: {
    image() {
      return this.pieces[this.selectedImage].imgURL
      
    }
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
  background-color: white;  
  position: relative;
}

button {
  font-size: 20px;
  text-align: center;
  align-items: center;
  display: flex;
  justify-content: space-evenly;


}

.sandwich-image {
  position: absolute;
  margin: 0 auto;
  
}



</style>
