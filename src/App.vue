<template>
  <div id="app" class="d-flex justify-content-center align-items-center vh-100">
    <Calculadora/>
  </div>
  <Informacoes/>
  <Rodape/>
</template>

<script>
import Calculadora from './components/calculadora.vue';
import Informacoes from './components/informacoes.vue';
import Rodape from './components/rodape.vue';

export default {
  name: 'App',
  components: {
    Calculadora,
    Informacoes,
    Rodape
  }
};
</script>

<style>
#app {
  width: 100%;
}
</style>