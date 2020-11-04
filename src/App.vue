<template>
  <div id="app">
    <app-input :numero1 = "numero1" :numero2 = "numero2" 
    @inputNumero1 = "numero1Mudou" @inputNumero2 = "numero2Mudou"/>
    <app-output :numero1 = "numero1" :numero2 = "numero2"/>
  </div>
</template>
<script>
import Input from './components/Input';
import Output from './components/Output';

export default {
  name: 'app',
  components: {
    'app-input': Input,
    'app-output': Output
  },
  data() {
    return {
      numero1 : 0,
      numero2 : 0 
    }
   },
  methods: {
    numero1Mudou(evento){
      this.numero1 = evento.target.value;
    },
    numero2Mudou(evento){
      this.numero2 = evento.target.value;
    }
  }
    
}
</script>