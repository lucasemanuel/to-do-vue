<template>
  <div id="app">
    <Header
      title="Minha Tarefas"
      sub_title="Não se esqueça das suas tarefas"
    ></Header>
    <main class="container is-max-widescreen">
      <Tasks />
    </main>
    <Footer />
  </div>
</template>

<script>
import Header from '../components/Header.vue';
import Tasks from '../components/Tasks.vue';
import Footer from '../components/Footer.vue';

export default {
  name: 'Home',
  components: {
    Header,
    Tasks,
    Footer,
  },
};
</script>

<style>
#app {
  font-family: "Sora", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

main.container {
  padding: 3rem 1.5rem;
}
</style>
