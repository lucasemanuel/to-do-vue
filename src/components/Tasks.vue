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
                      v-model="task_description"
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
        v-on:remove="remove(index)"
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
      task_description: '',
      tasks: [],
      last_id: 0,
    };
  },
  methods: {
    add() {
      const task = {
        id: this.last_id += 1,
        description: this.task_description,
        is_checked: 0,
      };
      this.tasks.splice(0, 0, task);
      this.last_id += 1;
      this.task_description = '';
    },
    check(index) {
      const task = this.tasks[index];
      task.is_checked = 1;
      this.remove(index);
      this.tasks.push(task);
    },
    remove(index) {
      this.tasks.splice(index, 1);
    },
  },
};
</script>

<style>
</style>
