<template>
  <button class="button" :disabled="disabled">
    <slot>Отправить</slot>
  </button>
</template>

<script>
export default {
  name: 'BaseButton',
  props: {
    disabled: Boolean
  }
}
</script>

<style lang="scss" scoped>
@import '@/styles/constants.scss';

$normal-bg-color: #0096da;
$hover-bg-color: #0081bc;
$pressed-bg-color: #015d87;

.button {
  height: $control-height-normal;
  padding: 22px 46px;
  border-style: none;
  border-radius: $control-height-normal / 2;
  background-color: $normal-bg-color;
  color: white;
  font-size: 16px;
  line-height: 0;
}
.button:hover {
  background-color: $hover-bg-color;
}
.button:focus {
  background-color: $pressed-bg-color;
}
.button:disabled {
  background-color: $disabled-bg-color;
  color: $disabled-text-color;
}
</style>
