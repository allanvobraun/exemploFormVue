<template>
  <div id="app">
    <formulario-do-json></formulario-do-json>
  </div>
</template>

<script>
import FormularioDoJson from '@/components/FormularioDoJson';

export default {
  name: 'App',
  components: {
    FormularioDoJson,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
