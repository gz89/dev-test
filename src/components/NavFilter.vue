<template>
  <div class="nav-filter">
    <h3 class="nav-filter-title">
      Filter
    </h3>
    <div class="filter-radio">
      <app-ratio name="radio" label="Natural" value="natural" v-model="radio" />
      <app-ratio
        name="radio"
        label="Lab Grown"
        value="labgrown"
        v-model="radio"
      />
    </div>
    <div class="filter-range">
      <h3 class="filter-range-title">Price</h3>
      <app-slider :min="0" :max="450" v-model="priceRange" />
      <div class="filter-range-minmax d-flex justify-content-between">
        <div>£{{ priceRange[0] }}</div>
        <div>£{{ priceRange[1] }}</div>
      </div>
    </div>
    <div class="filter-range">
      <h3 class="filter-range-title">
        <div>Caret</div>
        <img src="@/assets/Info.svg" alt="" srcset="" />
      </h3>
      <app-slider :min="0" :max="4" :interval="0.01" v-model="caretRange" />
      <div class="filter-range-minmax d-flex justify-content-between">
        <div>{{ caretRange[0] }}</div>
        <div>{{ caretRange[1] }}</div>
      </div>
    </div>
    <div class="filter-select">
      <h3 class="filter-select-title">
        <div>Clarity</div>
        <img src="@/assets/Info.svg" alt="" srcset="" />
      </h3>
      <div class="filter-select-items">
        <div
          class="filter-select-item"
          :class="{
            'filter-selected-item--selected': item === selectedClarity
          }"
          v-for="(item, index) in clarity"
          :key="index"
          @click="updateSelectedClarity(item)"
        >
          {{ item }}
        </div>
      </div>
    </div>
    <div class="filter-select">
      <h3 class="filter-select-title">
        <div>Colour</div>
        <img src="@/assets/Info.svg" alt="" srcset="" />
      </h3>
      <div class="filter-select-items">
        <div
          class="filter-select-item"
          :class="{
            'filter-selected-item--selected': item === selectedColour
          }"
          v-for="(item, index) in colour"
          :key="index"
          @click="updateSelectedColour(item)"
        >
          {{ item }}
        </div>
      </div>
    </div>
    <div class="filter-advanced">
      <a href="#">Show Advanced</a>
      <img src="@/assets/Reset.svg" alt="" />
    </div>
  </div>
</template>
<script>
import AppRadio from "@/components/AppRadio.vue";
import AppSlider from "@/components/AppSlider.vue";

export default {
  components: {
    "app-ratio": AppRadio,
    "app-slider": AppSlider
  },
  data() {
    return {
      priceRange: [10, 130],
      caretRange: [0.57, 2.47],
      clarity: ["SI1", "VS1", "VS2", "IF", "VVS2", "VVS1"],
      selectedClarity: "VS1",
      colour: ["K", "J", "I", "H", "G", "F", "E", "D"],
      selectedColour: "J",
      radio: "natural"
    };
  },
  methods: {
    updateSelectedClarity(item) {
      this.selectedClarity = item;
    },
    updateSelectedColour(item) {
      this.selectedColour = item;
    }
  }
};
</script>

<style>
.nav-filter {
  background: #fafafa;
  border-radius: 4px;
  padding: 23px 20px;
}

.nav-filter-title {
  font-size: 18px;
  line-height: 129.19%;
  color: #373737;
}
.filter-radio {
  margin-top: 26px;
}
.filter-range {
  margin-top: 35px;
}
.filter-range-title {
  display: flex;
  align-items: center;
  font-weight: 500;
  font-size: 13px;
  margin-bottom: 13px;
}
.filter-range-title div {
  margin-right: 6px;
}
.filter-range-minmax {
  font-size: 12px;
  line-height: 14px;
  color: #505050;
}
.filter-select {
  margin-top: 35px;
}
.filter-select-title {
  display: flex;
  align-items: center;
  font-weight: 500;
  font-size: 13px;
  margin-bottom: 13px;
}
.filter-select-title div {
  margin-right: 6px;
}
.filter-select-items {
  display: flex;
  flex-wrap: wrap;
}
.filter-select-item {
  font-size: 12px;
  line-height: 14px;
  text-align: center;
  color: #505050;
  border: 1px solid #e7e7e7;
  border-radius: 4px;
  padding: 5px 15px;
  margin-right: 7.5px;
  margin-bottom: 13px;
  cursor: pointer;
}
.filter-selected-item--selected {
  color: #fc8313;
  border-color: #fc8313;
}
.filter-advanced {
  margin-top: 28px;
  margin-bottom: 5px;
  display: flex;
  justify-content: space-between;
}
.filter-advanced a {
  font-size: 13px;
  text-decoration-line: underline;
  color: #7a7a7a;
}
</style>
