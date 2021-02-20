<template>
  <div class="app-header">
    <div class="app-subheader">
      <div
        class="container d-flex justify-content-between align-items-center flex-wrap"
      >
        <div class="app-subheader-item">
          <img src="@/assets/Video.svg" alt="" srcset="" />
          <span>Book a Virtual Consultation</span>
        </div>
        <div class="subheader-divider"></div>
        <div class="app-subheader-item">
          <img src="@/assets/Whatsapp.svg" alt="" srcset="" />
          <span>Contact a Specialist on WhatsApp</span>
        </div>
        <div class="subheader-divider"></div>
        <div class="app-subheader-item">
          <img src="@/assets/Click.svg" alt="" srcset="" />
          <span>Click and Collect</span>
        </div>
        <div class="subheader-divider"></div>
        <div class="app-subheader-item">
          <img src="@/assets/Phone.svg" alt="" srcset="" />
          <span>0800 080 3535</span>
        </div>
        <div class="subheader-divider"></div>
        <div class="app-subheader-item">
          <img src="@/assets/Location.svg" alt="" srcset="" />
          <span>Store Locations</span>
        </div>
      </div>
    </div>
    <div class="main-nav">
      <a
        v-if="isNavOpen"
        href="#"
        class="nav-item left-nav-mobile--body-close"
        @click="setNavOpen(false)"
        >Close</a
      >
      <div v-if="isNavOpen" class="left-nav-mobile--body">
        <a href="#" class="nav-item">Diamonds</a>
        <a href="#" class="nav-item nav-item--selected">Rings</a>
        <a href="#" class="nav-item">Jewellery</a>
        <a href="#" class="nav-item">Bespoke</a>
        <a href="#" class="nav-item nav-item--strong">Sale!</a>
        <a href="#" class="nav-item">My Account</a>
      </div>
      <b-container>
        <b-row class="d-flex">
          <b-col cols="2" md="5" sm="2">
            <div class="left-nav">
              <a href="#" class="nav-item">Diamonds</a>
              <a href="#" class="nav-item nav-item--selected">Rings</a>
              <a href="#" class="nav-item">Jewellery</a>
              <a href="#" class="nav-item">Bespoke</a>
              <a href="#" class="nav-item nav-item--strong">Sale!</a>
            </div>
            <div class="left-nav-mobile">
              <a
                href="#"
                class="nav-item left-nav-mobile--activator"
                @click="setNavOpen(true)"
                >Menu</a
              >
            </div>
          </b-col>
          <b-col cols="8" md="2" sm="8">
            <div class="main-logo">
              <img src="@/assets/Logo.svg" alt="" srcset="" />
            </div>
          </b-col>
          <b-col cols="2" md="5" sm="2">
            <div class="right-nav">
              <a href="#" class="nav-item">My Account</a>
              <a href="#" class="nav-item">
                <img src="@/assets/Cart.svg" alt="" srcset="" />
                My Cart</a
              >
            </div>
            <div class="right-nav-mobile">
              <a href="#" class="nav-item">
                <img src="@/assets/Cart.svg" alt="" srcset="" />
              </a>
            </div>
          </b-col> </b-row
      ></b-container>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      isNavOpen: false
    };
  },
  methods: {
    setNavOpen(isOpen) {
      this.isNavOpen = isOpen;
    }
  }
};
</script>
<style>
.app-subheader {
  display: flex;
  height: 42px;
  background: #202020;
}
.app-subheader-item {
  display: flex;
  align-items: center;
}
.app-subheader-item span {
  margin-left: 7px;
  font-size: 14px;
  line-height: 16px;
  color: #7a7a7a;
}
.subheader-divider {
  border: 1px solid #3c3c3c;
  height: 11px;
  width: 1px;
}
.main-nav {
  height: 86px;
  background: #252525;
}
.left-nav,
.left-nav-mobile {
  display: flex;
  align-items: center;
  flex-wrap: wrap;
  height: 100%;
}
.left-nav-mobile {
  display: none;
}
.left-nav-mobile--body {
  padding: 50px;
  position: absolute;
  width: 100vh;
  height: 100vh;
  background: #252525;
  z-index: 1000;
}
.left-nav-mobile--body-close {
  z-index: 1001;
  position: absolute;
  right: 0;
  top: 10px;
}

.nav-item {
  padding: 10px;
  margin-right: 24px;
  font-family: Roboto;
  font-style: normal;
  font-weight: normal;
  font-size: 14px;
  line-height: 16px;
  color: #e7e7e7;
  display: flex;
  align-items: center;
}
.nav-item img {
  margin-right: 10px;
}
.nav-item:hover {
  text-decoration: none;
  color: white;
}
.nav-item--selected {
  border-bottom: solid 2px #fc8313;
  color: white;
}
.nav-item--strong {
  color: #fc8313;
}
.main-logo {
  height: 86px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.right-nav,
.right-nav-mobile {
  display: flex;
  align-items: center;
  justify-content: flex-end;
  flex-wrap: wrap;
  height: 100%;
}
.right-nav-mobile {
  display: none;
}
.right-nav-mobile .nav-item {
  margin-right: 0;
}

@media (max-width: 575.98px) {
}

@media (max-width: 767.98px) {
}

@media (max-width: 991.98px) {
  .app-subheader {
    display: none;
  }
  .left-nav {
    display: none;
  }
  .left-nav-mobile {
    display: flex;
  }
  .right-nav {
    display: none;
  }
  .right-nav-mobile {
    display: flex;
  }
}

@media (max-width: 1199.98px) {
}

@media (max-width: 1399.98px) {
}
</style>
