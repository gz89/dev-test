<template>
  <label class="app-radio">
    <div class="label">{{ label }}</div>
    <input type="radio" :name="name" @change="handleInput" :checked="checked" />
    <span class="checkmark"></span>
  </label>
</template>
<script>
export default {
  name: "AppRadio",
  prop: ["val"],
  model: {
    prop: "selectedOption",
    event: "input"
  },
  props: {
    name: String,
    label: String,
    value: String
  },
  computed: {
    checked() {
      return this.value === this.$attrs["selectedOption"];
    }
  },
  methods: {
    handleInput() {
      this.$emit("input", this.value);
    }
  }
};
</script>
<style>
/* The app-radio */
.app-radio {
  position: relative;
  padding-left: 22px;
  cursor: pointer;
  margin-bottom: 5px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  margin-right: 22px;
}

/* Hide the browser's default radio button */
.app-radio input {
  position: absolute;
  opacity: 0;
  cursor: pointer;
}

.app-radio .label {
  font-family: Helvetica Neue;
  font-size: 12px;
  margin-top: -1.5px;
}

/* Create a custom radio button */
.app-radio .checkmark {
  position: absolute;
  top: 0;
  left: 0;
  height: 14px;
  width: 14px;
  background-color: #fff;
  border: solid 1px #e7e7e7;
  border-radius: 50%;
}

/* When the radio button is checked, add a blue background */
.app-radio input:checked ~ .checkmark {
  border: solid 1px #e37e1b;
}

/* Create the indicator (the dot/circle - hidden when not checked) */
.checkmark:after {
  content: "";
  position: absolute;
  display: none;
}

/* Show the indicator (dot/circle) when checked */
.app-radio input:checked ~ .checkmark:after {
  display: block;
}

/* Style the indicator (dot/circle) */
.app-radio .checkmark:after {
  top: 4px;
  left: 4px;
  width: 4px;
  height: 4px;
  border-radius: 50%;
  background: #e37e1b;
}
</style>
