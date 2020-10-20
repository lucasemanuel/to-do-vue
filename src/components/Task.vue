<template>
  <a class="panel-block" v-bind:class="checked_class">
    <a
      class="panel-icon has-text-success"
      v-on:click="$emit('check')"
      v-bind:class="checked_class"
    >
      <i class="fas fa-check" aria-hidden="true"></i>
    </a>
    {{ description }}
  </a>
</template>

<script>
export default {
  name: 'Task',
  props: {
    id: Number,
    description: String,
    is_complete: Number,
  },
  computed: {
    checked_class() {
      return {
        'has-text-grey-light': this.is_complete,
      };
    },
  },
};
</script>

<style>
a.panel-block {
  cursor: default;
}
</style>
