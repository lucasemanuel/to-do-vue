<template>
  <header class="hero is-primary is-bold">
    <div class="hero-body">
      <div class="container is-max-widescreen">
        <h1 class="title">{{ title }}</h1>
        <h2 class="subtitle">{{ sub_title }}</h2>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header',
  props: {
    title: String,
    sub_title: String,
  },
};
</script>

<style>
</style>
