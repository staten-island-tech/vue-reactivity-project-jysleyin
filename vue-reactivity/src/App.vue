<template>
  <div id="app">
   <h1>Mama's Sandwicheria</h1>

    <div id="sandwich" v-for = "(piece, index) in pieces" v-bind:key="piece.id" >
       <button @click="addClick(index)"> {{ piece.name }} </button> 
    </div>

    <div class="thing">
      <img class="sandwich-image" v-for = "piece in sandwich" :key="piece.id" :src = "piece"/>
    </div>
  
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
     this.sandwich.push(this.pieces[index].imgURL)
     console.log(this.sandwich)
    document.querySelector(".sandwich-image").style.transform = "translateY(4rem)";
    
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
  margin: auto 0;
  background-color: white;  
  position: relative;
}

#sandwich {
  display: flex;
  text-align: center;
  align-items: center;
  justify-content: space-evenly;
  flex-direction: row;


}

button {
  font-size: 1.25rem;
}

.sandwich-image {
  position: absolute;
  margin: 0 auto;
  
}

img {
width: 25rem;
}


</style>
