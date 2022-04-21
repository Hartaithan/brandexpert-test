<template>
  <div id="app">
    <History />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import History from './components/History.vue'

export default Vue.extend({
  name: 'App',
  components: {
    History
  }
})
</script>

<style lang="scss">
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: "Montserrat", sans-serif;
  color: #ffffff;
}
body {
  display: flex;
  flex-direction: column;
  background: #131426;
}
html,
body,
#app {
  height: 100%;
  width: 100%;
}
</style>
