<template>
  <div id="app">
    <AppHeader />
    <router-view />
    <AppFooter />
  </div>
</template>

<script>
import AppHeader from "@/components/AppHeader.vue";
import AppFooter from "@/components/AppFooter.vue";
export default {
  components: {
    AppHeader,
    AppFooter
  }
};
</script>

<style>
#app {
  font-family: Helvetica Neue;
}
@media (min-width: 1200px) {
  .container {
    max-width: 1229px !important;
  }
}
</style>
