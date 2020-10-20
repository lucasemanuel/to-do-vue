<template>
  <div id="app">
    <Header title="Minha Tarefas" sub_title="Não se esqueça das suas atividades"></Header>
    <h1>Minhas Tarefas</h1>
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import Header from '../components/Header.vue';
import HelloWorld from '../components/HelloWorld.vue';

export default {
  name: 'Home',
  components: {
    Header,
    HelloWorld,
  },
};
</script>

<style>
#app {
  font-family: 'Sora', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
