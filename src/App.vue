<template>
  <div id="app">
    <p>
      Novo curso:
      <input type="text" v-model="novo" />
      <button @click="incluir">Inserir</button>
    </p>
    <ul>
      <app-curso-item
        v-for="(curso, indice) in cursos"
        @click="excluir(indice)"
        :key="indice" :value = "curso.nome"
      >
       ({{indice}} - {{ curso.nome }})
      </app-curso-item>
      <component :is="componente" value="Fixo">( 9999 )</component>
    </ul>
  </div>
</template>
<script>
import CursoItem from './components/CursoItem';

export default {
  name: 'app',
  components: {
    'app-curso-item': CursoItem
  },
  data() {
    return {
      componente : 'app-curso-item',
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