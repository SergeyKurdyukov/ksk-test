<template>
  <label class="container">
    <div class="label">{{label}}</div>
    <input class="input" type="text"
      :placeholder="placeholder"
      :disabled="disabled"
      :required="required"/>
    <div class="error">{{error}}</div>
  </label>
</template>

<script>
export default {
  name: 'BaseTextField',
  props: {
    disabled: Boolean,
    label: String,
    placeholder: String,
    required: Boolean,
    error: String
  }
}
</script>

<style lang="scss" scoped>
$common-color: #dadef0;
$hover-color: #c3c9db;
$focus-color: #8288a2;
$disabled-color: #edeeef;
$disabled-color-text: #b8bed8;
$invalid-color: #ff1e38;

.container {
  display: inline-block;

  .label {
    text-align: left;
    margin-bottom: 10px;
  }

  .input {
    border-radius: 4px;
    border: 1px solid $common-color;
    height: 56px;
    padding: 0 20px;
  }
  .input:hover:not(:disabled):not(:invalid) {
    border-color: $hover-color;
  }
  input:focus {
    border-color: $focus-color;
  }
  input:disabled {
    background-color: $disabled-color;
    border-color: $disabled-color;
  }
  // TODO: make disabled label as gray
  input:invalid {
    border-color: $invalid-color;
  }
  input:invalid + .error {
    display: block;
  }

  .error {
    display: none;
    text-align: left;
    color: $invalid-color;
    font-size: 12px;
    line-height: 20px;
  }
}

</style>
