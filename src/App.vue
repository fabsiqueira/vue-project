<template>
  <div id="app">
    <app-input />
    <app-output />
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
  }
    
}
</script>