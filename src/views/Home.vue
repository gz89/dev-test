<template>
  <div class="home">
    <b-container>
      <b-row>
        <b-col cols="12" sm="6" md="4" lg="3">
          <NavFilter />
        </b-col>
        <b-col cols="12" sm="6" md="8" lg="9">
          <ProductLists />
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import NavFilter from "@/components/NavFilter.vue";
import ProductLists from "@/components/ProductLists.vue";

export default {
  name: "Home",
  components: {
    NavFilter,
    ProductLists
  }
};
</script>

<style>
.home {
  margin-top: 63px;
}
</style>
