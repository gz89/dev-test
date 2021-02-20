<template>
  <div class="product-lists">
    <a href="#" class="bread-crumbs">
      <img src="@/assets/ChevronLeft.svg" alt="" srcset="" />
      Back to Engagment Rings
    </a>
    <h2 class="product-lists-header">Select Your Diamond</h2>
    <p class="product-lists-header-description">
      18ct White Gold Round Brilliant Simplicity Engagement Ring
    </p>
    <div class="product-lists-filter">
      <app-input placeholder="Diamond ID" />
      <div class="product-lists-filter-controls">
        <app-checkbox label="With Images" v-model="withImages" />
        <app-checkbox label="With Videos" v-model="withVideos" />
        <app-checkbox label="Show Advanced" v-model="showAdvanced" />
        <div class="filter-divider"></div>
        <div class="grid-mode-control" @click="updateDisplayMode('grid')">
          <grid-icon :color="displayMode === 'grid' ? '#FC8313' : '#252525'" />
        </div>
        <div class="grid-mode-control" @click="updateDisplayMode('list')">
          <list-icon :color="displayMode === 'list' ? '#FC8313' : '#252525'" />
        </div>
      </div>
    </div>
    <b-row class="d-flex product-lists-grid">
      <b-col
        cols="12"
        lg="6"
        xl="4"
        v-for="(product, index) in products"
        :key="index"
      >
        <product-card
          :price="product.price"
          :ct="product.ct"
          :imgURL="product.img"
          :compare="product.compare"
        />
      </b-col>
    </b-row>
  </div>
</template>
<script>
import AppInput from "@/components/AppInput.vue";
import ProductCard from "@/components/ProductCard.vue";
import Image from "@/assets/Diamond.png";
import GridIcon from "./GridIcon.vue";
import ListIcon from "./ListIcon.vue";
import AppCheckbox from "@/components/AppCheckbox.vue";

export default {
  components: {
    "app-input": AppInput,
    "product-card": ProductCard,
    "grid-icon": GridIcon,
    "list-icon": ListIcon,
    "app-checkbox": AppCheckbox
  },
  data() {
    return {
      withImages: true,
      withVideos: false,
      showAdvanced: false,
      displayMode: "grid",
      products: [
        {
          img: Image,
          price: "£2,465.03",
          ct: "0.81ct",
          compare: false
        },
        {
          img: Image,
          price: "£2,465.03",
          ct: "0.81ct",
          compare: true
        },
        {
          img: Image,
          price: "£2,465.03",
          ct: "0.81ct",
          compare: false
        },
        {
          img: Image,
          price: "£2,465.03",
          ct: "0.81ct",
          compare: false
        },
        {
          img: Image,
          price: "£2,465.03",
          ct: "0.81ct",
          compare: false
        },
        {
          img: Image,
          price: "£2,465.03",
          ct: "0.81ct",
          compare: false
        },
        {
          img: Image,
          price: "£2,465.03",
          ct: "0.81ct",
          compare: false
        },
        {
          img: Image,
          price: "£2,465.03",
          ct: "0.81ct",
          compare: false
        },
        {
          img: Image,
          price: "£2,465.03",
          ct: "0.81ct",
          compare: true
        },
        {
          img: Image,
          price: "£2,465.03",
          ct: "0.81ct",
          compare: false
        },
        {
          img: Image,
          price: "£2,465.03",
          ct: "0.81ct",
          compare: false
        }
      ]
    };
  },
  methods: {
    updateDisplayMode(mode) {
      this.displayMode = mode;
    }
  }
};
</script>
<style>
.bread-crumbs {
  font-family: Roboto;
  font-size: 13px;
  line-height: 147.69%;
  color: #7a7a7a;
  text-decoration: none;
}
.bread-crumbs:hover {
  text-decoration: none;
  color: #fc8313;
}
.bread-crumbs img {
  margin-right: 8px;
}
.product-lists-header {
  margin-top: 10px;
  font-size: 24px;
  line-height: 129.19%;
  color: #252525;
}
.product-lists-header-description {
  font-family: Helvetica Neue;
  font-size: 18px;
  line-height: 129.19%;
  color: #505050;
}
.product-lists-filter {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  margin-top: 33px;
  padding-bottom: 22px;
  border-bottom: 1px solid #e7e7e7;
}
.product-lists-filter-controls {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: center;
}
.grid-mode-control {
  cursor: pointer;
  margin-left: 18px;
  display: flex;
  align-items: center;
}
.product-lists-grid {
  margin-top: 22px;
}
.filter-divider {
  height: 14px;
  width: 1px;
  border: solid 1px #e7e7e7;
}

@media (max-width: 575.98px) {
}

@media (max-width: 767.98px) {
  .product-lists-filter-controls .app-checkbox {
    margin: 0 15px;
  }
}
@media (max-width: 991.98px) {
  .product-lists-filter .app-input {
    margin-bottom: 15px;
  }
}
</style>
