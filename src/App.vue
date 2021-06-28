<template>
  <div id="app">
    <BaseRadioButton name="address">Radio normal</BaseRadioButton>
    <br/>
    <BaseRadioButton name="address">Radio hover</BaseRadioButton>
    <br/>
    <BaseRadioButton name="address" checked>Radio selected</BaseRadioButton>
    <br/>
    <BaseRadioButton name="address" disabled>Radio disabled</BaseRadioButton>

    <br/>
    <br/>
    <br/>
    <BaseTextField label="Input" placeholder="Some placeholder"></BaseTextField>
    <br/>
    <BaseTextField label="Input" placeholder="Some placeholder" disabled></BaseTextField>
    <br/>
    <BaseTextField label="Input" placeholder="Some placeholder" required error="Error message"></BaseTextField>

  </div>
</template>

<script>
import BaseRadioButton from './components/BaseRadioButton.vue'
import BaseTextField from './components/BaseTextField.vue'

export default {
  name: 'App',
  components: {
    BaseRadioButton,
    BaseTextField
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@500&display=swap');

* {
  box-sizing: border-box;
  font-family: 'Montserrat', sans-serif;
  font-size: 14px;
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
