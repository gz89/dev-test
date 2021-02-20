<template>
  <vue-slider
    class="app-slider"
    v-bind="$attrs"
    :contained="true"
    @change="handleInput"
    tooltip="none"
    :height="19"
    :railStyle="{
      height: '4px',
      left: '0px',
      top: '7px',
      background: '#EDEDED'
    }"
    :processStyle="{
      background: 'linear-gradient(90deg, #E77E18 4.89%, #FFA34A 99.44%)',
      'border-radius': '17px'
    }"
    :dotSize="['10', '19']"
  >
    <template v-slot:dot="{ focus }">
      <div :class="['custom-dot', { focus }]">
        <div class="custom-dot-inner"></div>
      </div>
    </template>
  </vue-slider>
</template>
<script>
export default {
  methods: {
    handleInput(value) {
      this.$emit("input", value);
    }
  }
};
</script>
<style>
.app-slider.vue-slider {
  padding: 4px 5px !important;
}
.custom-dot {
  height: 19px;
  background: #ffffff;
  box-shadow: 0px 0px 1.26667px rgba(0, 0, 0, 0.2),
    0px 2.53333px 7.6px rgba(0, 0, 0, 0.06);
  border-radius: 4px;
  padding: 5px 4px;
}
.custom-dot.focus .custom-dot-inner {
  background: #ededed;
}
.custom-dot-inner {
  background: white;
  width: 100%;
  height: 100%;
}
</style>
