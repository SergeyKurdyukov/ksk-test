<template>
  <div id="app">

    <BaseTabs :tabs="tabs"></BaseTabs>
    <br/>
    <br/>

    <BaseButton>Button normal</BaseButton>
    <br/>
    <BaseButton disabled>Button disabled</BaseButton>
    <br/>
    <br/>

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
import BaseButton from './components/BaseButton.vue'
import BaseTabs from './components/BaseTabs.vue'
import DeliveryForm from './components/DeliveryForm.vue'
import DeliveryMap from './components/DeliveryMap.vue'

export default {
  name: 'App',
  components: {
    BaseRadioButton,
    BaseTextField,
    BaseButton,
    BaseTabs
  },
  data: function () {
    return {
      tabs: [
        {
          name: 'One',
          component: DeliveryForm
        },
        {
          name: 'Two',
          component: DeliveryMap
        },
        {
          name: 'Three',
          component: DeliveryForm
        },
        {
          name: 'Four',
          component: DeliveryMap
        }
      ]
    }
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
