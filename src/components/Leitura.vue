<template>
  <div>
    <button @click="handleFile">click</button>
    <div v-for="items in handleFile" :key="items.id">
      <div v-for="item in items" :key="item.id">
        <div class="texto" v-for="linha in item" :key="linha.id">
          {{ linha }}
        </div>
      </div>
      
    </div>
  </div>
</template>

<script>
export default {
  props: ["livro"],
  data() {
    return {
      dados: [],
    };
  },
  computed: {
    handleFile() {    
      return require(`../../data/${this.livro}`);
      
    },
  },
};
</script>

<style  scoped>
.texto {
  font-size: calc(60% + 0.8vmin);
}
</style>