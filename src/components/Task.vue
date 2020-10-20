<template>
  <a class="panel-block">
    <a class="panel-icon">
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
    is_complete: Boolean,
  },
};
</script>

<style>
a.panel-block {
  cursor: default;
}
</style>
