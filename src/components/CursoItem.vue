<template>
  <li @click= "itemClicado">  
    {{value}} - <slot/>
    </li>
</template>

<script>
export default {
    name: 'CursoItem',
    // receber parametro em componente
    props: {
      value: String
    },
    methods: {
      itemClicado(evento){
        this.$emit('click', evento);
      }
    }
    }
</script>