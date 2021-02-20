<template>
  <div class="app-input">
    <img src="@/assets/Search.svg" alt="" srcset="" />
    <b-form-input type="text" v-bind="$attrs" />
  </div>
</template>
<style>
.app-input {
  display: block;
  width: 150px;
}
.app-input img {
  position: absolute;
  margin: 8.5px 16px;
}
.app-input input {
  padding: 0 10px 0 40px;
  height: 30px;
  background: #ffffff;
  border: 1px solid #ededed;
  box-sizing: border-box;
  border-radius: 100px;

  font-family: Helvetica Neue;
  font-size: 12px;
  line-height: 14px;
  letter-spacing: 0.105em;

  /* Grey/Grey-300 */

  color: #7a7a7a;
}
.app-input input:focus {
  box-shadow: none;
  border-color: #fc8313;
}
@media (max-width: 991.98px) {
  .app-input {
    width: 100%;
  }
}
</style>
