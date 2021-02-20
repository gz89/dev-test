<template>
  <div class="product-card">
    <div class="product-card-top">
      <app-checkbox label="Compare" v-model="compare" />
      <a href="#">More Info</a>
    </div>
    <img :src="imgURL" width="84px" height="84px" alt="" srcset="" />
    <div class="product-card-price">{{ price }}</div>
    <div class="product-card-ct">{{ ct }}</div>
    <app-button variant="primary" class="product-card-btn">Choose</app-button>
  </div>
</template>
<script>
import AppButton from "@/components/AppButton.vue";
import AppCheckbox from "@/components/AppCheckbox.vue";

export default {
  components: {
    "app-button": AppButton,
    "app-checkbox": AppCheckbox
  },
  props: {
    price: String,
    ct: String,
    imgURL: String,
    compare: Boolean
  }
};
</script>
<style>
.product-card {
  height: 262px;
  background: #fafafa;
  border-radius: 10px;
  margin-bottom: 22px;
  padding: 13px 15px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.product-card img {
  margin-top: 20px;
}
.product-card-top {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.product-card-top a {
  font-size: 12px;
  text-decoration-line: underline;
  color: #505050;
}
.product-card-price {
  margin-top: 15px;
  font-size: 16px;
  font-weight: bold;
  line-height: 129.19%;
  text-align: center;
  color: #252525;
}
.product-card-ct {
  margin-top: 8px;
  font-size: 12px;
  line-height: 14px;
  text-align: right;
  color: #505050;
}
.product-card-btn {
  margin-top: 15px;
}
</style>
