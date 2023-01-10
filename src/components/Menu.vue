<template>
  <div>
    Menu
    <button @click="getFilesList">clique</button>
    <List @setlivro='setlivro' :items="items" />
    <Leitura :livro="livro" />
  </div>
</template>

<script>
import List from "./List.vue";
import Leitura from './Leitura.vue'
export default {
  components: {
    List,
    Leitura,
    
  },
  data() {
    return {
      items: [],
      livro:'',
    };
  },

  methods: {
    setlivro(i){      
      this.livro = i;
    },
    getFilesList() {
      this.items = [];
      const files = require.context("@../../../data/", true);
      //console.log(files.keys())
      let count = 0;
      let id = 1;
      var nome;
      files.keys().forEach((element) => {
        count++;
        if (count == 1) {
          nome = element;
        }
        if (count == 2) {
          var arquivo = element;
        }

        if (count == 2) {
          let livro = {
            id: id,
            nome: nome.substring(2),
            arquivo: arquivo.substring(2),
          };
          this.items.push(livro);

          count = 0;
          id++;
        }
      });
      
    },
  },
};
</script>

<style scoped>
</style>