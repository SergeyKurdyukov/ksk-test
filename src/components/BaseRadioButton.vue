<template>
  <label class="radio-container">
    <input class="radio-input visually-hidden" type="radio"
      :checked="checked"
      :disabled="disabled"
      :name="name">
    <div class="radio-button">
      <span class="radio-button__mark"></span>
    </div>
    <span class="label">
      <slot></slot>
    </span>
  </label>
</template>

<script>
export default {
  name: 'BaseRadioButton',
  props: {
    checked: Boolean,
    disabled: Boolean,
    name: String
  }
}
</script>

<style lang="scss" scoped>
@import '@/styles/constants.scss';

$label-margin: 14px;
$normal-color: #dbdff0;
$selected-color: #0698db;

.visually-hidden {
  position: absolute;
  width: 1px;
  height: 1px;
  margin: -1px;
  border: 0;
  padding: 0;
  clip: rect(0 0 0 0);
  overflow: hidden;
}

.radio-button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  border: 1px solid $normal-color;
  position: absolute;
  border-radius: 10px;
  height: 20px;
  width: 20px;

  .radio-button__mark {
    display: block;
    width: 6px;
    height: 6px;
    border-radius: 3px;
  }
}

.label {
  padding-left: $label-margin * 2;
}

.radio-input:hover:not(:disabled) + .radio-button {
  border-color: $selected-color;
}
.radio-input:hover:not(:disabled) ~ .label {
  color: $selected-color;
}

.radio-input:disabled + .radio-button {
  background-color: $disabled-bg-color;
  border-color: $disabled-bg-color;
}
.radio-input:disabled ~ .label {
  color: $disabled-text-color;
}

.radio-input:checked + .radio-button {
  border-color: $selected-color;
  .radio-button__mark {
    background-color: $selected-color;
  }
}
</style>
