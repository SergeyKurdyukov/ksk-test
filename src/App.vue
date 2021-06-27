<template>
  <div id="app">
    <BaseRadioButton name="address">Radio normal</BaseRadioButton>
    <br/>
    <BaseRadioButton name="address">Radio hover</BaseRadioButton>
    <br/>
    <BaseRadioButton name="address" checked>Radio selected</BaseRadioButton>
    <br/>
    <BaseRadioButton name="address" disabled>Radio disabled</BaseRadioButton>
  </div>
</template>

<script>
import BaseRadioButton from './components/BaseRadioButton.vue'

export default {
  name: 'App',
  components: {
    BaseRadioButton
  }
}
</script>

<style lang="scss">
* {
  box-sizing: border-box;
  font-family: "Montserrat";
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
