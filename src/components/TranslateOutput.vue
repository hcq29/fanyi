<template>
  <div id="translateOutput">
    <h1>{{translatedText}}</h1>
  </div>
</template>

<script>

export default {
  name: 'App',
  props: [
      "translatedText"
  ],
  components: {
  }
}
</script>

<style>
#translateOutput {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
