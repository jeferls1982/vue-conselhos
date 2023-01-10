<template>
  <div id="app">
    <span v-for="item in items" :key="item.id">
        <div @click="showLivro(item.arquivo)" class="item">{{ item.nome }}</div>
    </span>
  </div>
</template>

<script>
export default {
  props: ["items"],
  methods:{
      showLivro(item){
          this.$emit('setlivro', item)
      }
  }
};
</script>

<style scoped>
#app{
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    
}
.item{
    font-size: 12px;
    color: rgb(104, 101, 101);
    padding: 12px ;
    background-color: rgba(128, 128, 128, 0.274);
    width: 130px;
    margin:5px;
    text-align: center;
    border-radius: 10px;
    box-shadow: 2px 2px 2px rgba(128, 128, 128, 0.644);
   
    
}
</style>