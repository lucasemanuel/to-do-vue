<template>
  <a class="panel-block" v-bind:class="checked_class">
    <span
      class="check has-text-success mr-3"
      v-on:click="$emit('check')"
      v-bind:class="checked_class"
    >
      <i class="fas fa-check" aria-hidden="true"></i>
    </span>
    <span>
      {{ description }}
    </span>
    <span class="has-text-right is-pulled-right">
      <a class="has-text-danger ml-3" v-on:click="$emit('remove')">
        <i class="fas fa-times" aria-hidden="true"></i>
      </a>
    </span>
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
  display: block;
  cursor: default;
}

span.check {
  cursor: pointer;
}
</style>
