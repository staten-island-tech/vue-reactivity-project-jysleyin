<template>

<div id="app">

   <h1>Mama's Sandwicheria</h1>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Raleway:wght@500&family=Source+Sans+Pro&display=swap" rel="stylesheet">

  <div class="row">
    <div id="sandwich" v-for = "(piece, index) in pieces" v-bind:key="piece.id" >
       <button class="buttons" @click="addClick(index)"> {{ piece.name }} </button> 
    </div>
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
    document.querySelector(".sandwich-image").style.transform = "translateY(3rem)";
    
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
background-color: #5f380d;
font-family: 'Source Sans Pro', sans-serif;
}

#app {
  color: #9d5836;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin: 10rem;
  background-color: #F1AB86;  
  position: relative;
  padding: 0 0 30rem 0;
}


button {
  font-size: 1.25rem;
  display: inline-block;
  padding:0.3em 1.2em; 
  margin:0 0.1em 0.1em 0; 
  border:0.16em solid rgba(255,255,255,0); 
  border-radius:2em; 
  box-sizing: border-box; 
  font-family: 'Raleway', sans-serif;
  font-weight:300; 
  color:#F7DBA7; 
  text-shadow: 0 0.04em 0.04em rgba(0,0,0,0.35); 
  text-align:center; 
  transition: all 0.2s;
  background-color: #9CAFB7;

}

button:hover{
 border-color: rgba(255,255,255,1);
}

.thing {
  text-align: center;
  display: flex;
  justify-content: center;
}
.sandwich-image {
  position: absolute;
  margin: 0 auto;
  padding: 4rem;
}

.row {
display: flex;
flex-direction: row;
text-align: center;
justify-content: space-evenly;

}

img {
width: 25rem;
}


</style>
