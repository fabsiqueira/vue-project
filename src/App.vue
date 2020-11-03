<template>
<div id="app">
  <p>Novo curso:
    <input type="text" v-model="novo">
    <button @click="incluir">Inserir</button>
    </p>
    <ul>
      <li v-for="(curso, indice) in cursos" @click="excluir(indice)" :key="indice">
        {{curso.nome}}
        </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: "app",
  data() {
    return {
      novo: "",
      cursos: [{ nome: "ADS" }, { nome: "Banco de Dados" }],
    };
  },
  methods: {
    incluir() {
      if (this.novo.trim().length == 0) {
        alert("O nome do curso deve ser preenchido!");
      } else {
        this.cursos.push({ nome: this.novo });
      }
    },
    excluir(indice) {
      this.cursos.splice(indice, 1);
    },
  },
};
</script>