<template>
  <b-button class="app-button" v-bind="$attrs">
    <slot />
  </b-button>
</template>
<style>
.app-button.btn {
  font-family: Roboto;
  border-radius: 10px;
  font-size: 12px !important;
  padding: 10px 52px !important;
  color: #ffffff;
  outline: 0;
  border-color: #fc8313;
}
.app-button.btn-primary {
  background-color: #fc8313 !important;
  border-color: #fc8313 !important;
}
.app-button.btn-primary:focus,
.app-button.btn-primary:hover {
  background: #e77e18;
  box-shadow: 0px 3px 20px rgba(231, 126, 24, 0.3);
}
.app-button.btn-primary:focus {
  background: #e77e18;
}
.app-button.btn:active:focus {
  box-shadow: unset;
}
</style>
