<template>
  <footer class="footer">
    <div class="content has-text-centered">
      <p>
        <strong>To do Vue</strong>
        (<a href="https://github.com/lucasemanuel/to-do-vue/">repo</a>) by
        <a href="https://github.com/lucasemanuel">Lucas Emanuel</a> -
        {{ getYear() }}
      </p>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'Footer',
  methods: {
    getYear() {
      const today = new Date();
      return today.getFullYear();
    },
  },
};
</script>

<style>
footer {
  background: none;
}
</style>
