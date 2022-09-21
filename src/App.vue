<script>
import axios from "axios";
export default {
data() {
  return {
    cep: "",
    endereço: {},
  };
},
methods: {
  async buscar() {
    const url = `https://www.viacep.com.br/ws/$(this.cep)/json/`;
    const res = await axios.get(url);
    this.endereço = res.data;
  }
},
};
</script>

<template>
  <main>
    <h1>Busca CEP</h1>
    <form @submit.prevent="buscar"></form>
  </main>
</template>