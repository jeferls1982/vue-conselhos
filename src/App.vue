<template>
  <div id="app">
    <meta http-equiv="Content-Language" content="en">
    <meta name="theme-color" content="#C51162" />
    <Navbar />
    <div class="boneco">
      <Boneco @setConselho="setConselho" />
    </div>

    <div class="conselhos">
      <div v-for="item in items" :key="item.id">
        <div class="item">
           {{ item }}
        </div>       
      </div>
    </div>
    <Menu />
    
  </div>
</template>

<script>


import Navbar from "./components/parts/Navbar.vue";
import Boneco from "./components/parts/Boneco.vue";
import Menu from './components/Menu.vue'

export default {
  name: "App",
  
  components: {
   Menu,
    Navbar,
    Boneco,
    
  },
  data() {
    return {
      items: [],
    };
  },
  methods:{
    setConselho(i){     
      
       this.items.unshift(i);
       //console.log(JSON.stringify(teste))
    }
  }
};
</script>

<style scoped>
#app {
  margin: 0;
  padding: 0;
  border: 0;

  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  height: 100vh;
}
.item{
  margin: 10px;
  border: 1px solid rgba(128, 128, 128, 0.637);
  box-shadow: 3px 3px 3px rgba(128, 128, 128, 0.472);
  padding: .5rem;
  color: rgb(83, 82, 82);
  border-radius: 5px;
}
</style>
