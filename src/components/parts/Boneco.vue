<template>
  <div class="personagem">
    <img src="../../assets/idea.jpg" alt="" width="100" />
    <div class="instrucao">
      <span @click="getConselho" class="texto"> Quer uma dica?</span>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  methods: {
    async getConselho() {
      await axios.get("	https://api.adviceslip.com/advice").then((response) => {
        console.log(response.data.slip.advice);
        this.$emit("setConselho", response.data.slip.advice);

       
      });
    },
  },
};
</script>

<style scoped>
.personagem {
  display: flex;
  justify-content: center;
}
.instrucao {
  display: flex;
  justify-content: start;
  align-items: center;
}
.texto {
  text-align: center;
  border: 2px solid rgba(128, 128, 128, 0.308);
  padding: 0.5rem;
  border-radius: 10px;
  box-shadow: 3px 3px 3px rgba(128, 128, 128, 0.281);
  background-color: #ff80ab;
  color: white;
}
</style>