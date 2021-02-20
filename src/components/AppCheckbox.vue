<template>
  <label class="app-checkbox">
    <div class="label">{{ label }}</div>
    <input type="checkbox" @input="handleInput" :checked="value" />
    <span class="checkmark"></span>
  </label>
</template>
<script>
export default {
  name: "AppCheckbox",
  props: {
    label: String,
    value: Boolean
  },
  methods: {
    handleInput() {
      this.$emit("input", this.value);
    }
  }
};
</script>
<style>
/* The app-checkbox */
.app-checkbox {
  position: relative;
  padding-left: 22px;
  cursor: pointer;
  margin-bottom: 0px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  margin-right: 22px;
}

/* Hide the browser's default radio button */
.app-checkbox input {
  position: absolute;
  opacity: 0;
  cursor: pointer;
}

.app-checkbox .label {
  font-family: Helvetica Neue;
  font-size: 12px;
  margin-top: -1.5px;
}

.app-checkbox .checkmark {
  position: absolute;
  top: 0;
  left: 0;
  height: 14px;
  width: 14px;
  background-color: #fff;
  border: solid 1px #e7e7e7;
  border-radius: 4.66667px;
}

/* When the radio button is checked, add a blue background */
.app-checkbox input:checked ~ .checkmark {
  border: solid 1px #e37e1b;
}

/* Create the indicator (the dot/circle - hidden when not checked) */
.checkmark:after {
  content: "";
  position: absolute;
  display: none;
}

/* Show the indicator (dot/circle) when checked */
.app-checkbox input:checked ~ .checkmark:after {
  display: block;
}

/* Style the indicator (dot/circle) */
.app-checkbox .checkmark:after {
  top: 4px;
  left: 4px;
  width: 4px;
  height: 4px;
  border-radius: 4.66667px;
  background: #e37e1b;
}
</style>
