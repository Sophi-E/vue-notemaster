<template>
  <div id="app">
    <h3>NOTEMASTER</h3>
    <notes />
  </div>
</template>

<script>
import Notes from './components/Notes.vue'
export default {
  name: 'app',
  components: {
    Notes
  }
}
</script>

<style>
  body{
    padding: 0.5rem;
    word-wrap: break-word
  }
</style>
