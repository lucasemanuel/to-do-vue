<template>
  <div id="app">
    <Header
      title="Minha Tarefas"
      sub_title="Não se esqueça das suas atividades"
    ></Header>
    <main class="container is-max-widescreen">
      <div class="box">
        <article class="media">
          <div class="media-content">
            <div class="content">
              <form v-on:submit.prevent="onSubmit">
                <div class="field">
                  <label for="task" class="label">Adicione sua tarefa</label>
                  <div class="field has-addons">
                    <div class="control is-expanded">
                      <input
                        class="input"
                        type="text"
                        name="task"
                        id="task"
                        placeholder="ex: Tirar o lixo"
                        v-model="task"
                      />
                    </div>
                    <div class="control">
                      <input type="submit" class="button is-primary" value="Salvar"/>
                    </div>
                  </div>
                </div>
              </form>
            </div>
          </div>
        </article>
      </div>
    </main>
  </div>
</template>

<script>
import Header from '../components/Header.vue';

export default {
  name: 'Home',
  components: {
    Header,
  },
  data() {
    return {
      task: '',
    };
  },
  methods: {
    onSubmit() {
      console.log(this.task);
    },
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
