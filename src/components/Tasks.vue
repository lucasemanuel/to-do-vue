<template>
  <section id="tasks">
    <div class="box">
      <article class="media">
        <div class="media-content">
          <div class="content">
            <form v-on:submit.prevent="add">
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
                    <input
                      type="submit"
                      class="button is-primary"
                      value="Salvar"
                    />
                  </div>
                </div>
              </div>
            </form>
          </div>
        </div>
      </article>
    </div>
    <article class="panel is-primary">
      <p class="panel-heading">Tarefas</p>
      <Task
        v-for="(item, index) in tasks"
        v-bind:key="item.id"
        v-bind:index="index"
        v-bind:description="item.description"
        v-bind:is_complete="item.is_checked"
        v-on:check="check(index)"
      ></Task>
    </article>
  </section>
</template>

<script>
import Task from './Task.vue';

export default {
  name: 'Tasks',
  components: {
    Task,
  },
  data() {
    return {
      task: '',
      tasks: [],
      last_id: 0,
    };
  },
  methods: {
    add() {
      this.tasks.push({
        id: this.last_id += 1,
        description: this.task,
        is_checked: 0,
      });
      this.last_id += 1;
    },
    check(index) {
      this.tasks[index].is_checked = 1;
    },
  },
};
</script>

<style>
</style>
