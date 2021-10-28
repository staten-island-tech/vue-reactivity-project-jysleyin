<template>
  <div id="app">
   <h1>Mama's Sandwicheria</h1>
    <div id="sandwich" v-for = "(piece, index) in pieces" v-bind:key="piece.id" >
       <button @click="addClick(index)"> {{ piece.name }} </button> 
    </div>
    <div class="sandwich-image" > 
      
      <!-- @add-click = "buildWich" -->
    <img :src = "image"/>
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

  sandwich: []

  }
  },
  methods: {
    
    buildWich(index){
      this.sandwich.push(index)
    },

    addClick(index){
    // this.$emit('add-click');
     this.selectedImage = index;
     console.log(index)
    
    // index.insertAdjacentHTML("beforebegin", this.pieces[this.selectedImage].imgURL)
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

}

button {
  font-size: 20px;

}


</style>
