<template>
  <div class="container">
    <button v-for="(tab, index) in tabs"
      :key="index"
      @click="activeTab = tab"
      class="tab-label"
      :class="[activeTab === tab ? 'active' : '']">
      <span class="tab-name">{{tab.name}}</span>
    </button>
    <transition name="tab-panel-appearance" mode="out-in">
      <component :is="activeTab.component"></component>
    </transition>
  </div>
</template>

<script>

export default {
  props: {
    tabs: Array
  },
  data: function () {
    return {
      activeTab: null
    }
  },
  created: function () {
    this.activeTab = this.tabs[0]
  }
}
</script>

<style lang="scss" scoped>
@import '@/styles/constants.scss';

$border-radius: 6px;
$border-color: #dedfe0;
$degree: 30deg;
$active-color: #44b2e4;

.container {
  background-color: tomato;
}

.tab-label {
  background-color: $disabled-bg-color;
  color: $focus-color;
  cursor: pointer;
  border-width: 0 1px 0 0;
  border-color: $border-color;
  border-top-left-radius: $border-radius * 2;
  border-top-right-radius: $border-radius;
  height: 64px;
  width: 173px;
  transform: skewX($degree);

  .tab-name {
    display: block;
    transform: skewX(-$degree);
  }
}

.tab-label.active {
  background-color: white;
  .tab-name {
    color: $active-color;
  }
}
.tab-label.active::before{
  background-color: white;
  border-left-color: transparent;
  display: block;
}
.tab-label.active + .tab-label::before {
  display: none;
}

/* Left side of a tab */
.tab-label::before {
  display: none;
  content: "";
  width: 40px;
  height: 100%;
  transform: skewX(-$degree);
  position: absolute;
  left: -16px;
  top: 0;
  background-color: $disabled-bg-color;
  border-left: 1px solid $border-color;
  border-top-left-radius: $border-radius;
}
.tab-label:first-child::before {
  display: block;
}

/* Animation */
.tab-panel-appearance-enter-active, .tab-panel-appearance-leave-active {
  transition: opacity .3s ease;
}
.tab-panel-appearance-enter, .tab-panel-appearance-leave-to {
  opacity: 0;
}

</style>
