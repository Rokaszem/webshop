<template>
  <div id="nav">
    <div class="nav-logo">
      <img
        src="https://upload.wikimedia.org/wikipedia/commons/2/2f/Google_2015_logo.svg"
      />
    </div>
    <ul class="nav-links">
      <li><router-link to="#">Dashboard</router-link></li>
      <li><router-link to="#">Products</router-link></li>
      <li><div id="cart-btn" @click="openCart">Cart</div></li>
    </ul>
  </div>
  <div class="cart-panel" v-show="toggleCart">
    <div class="cart">
      <div>Cart</div>
      <CartItem />
    </div>
    <div class="inactive" @click="openCart"></div>
  </div>
</template>

<script>
export default {
  name: "NavigationBar",
  data() {
    return {
      toggleCart: false,
      cartItems: [],
    };
  },
  methods: {
    openCart() {
      this.toggleCart = !this.toggleCart;
      console.log(this.toggleCart);
    },
    async getData() {
      try {
        let response = await fetch("https://fakestoreapi.com/carts/1");
        this.list = await response.json();
      } catch (error) {
        console.log(error);
      }
    },
  },
};
</script>

<style scoped>
a:-webkit-any-link {
  text-decoration: none;
}
/*#region Navigation*/
#nav {
  height: 30px;
  padding-top: 15px;
  background-color: aquamarine;
  border-bottom: black solid 1px;
}
.nav-logo {
  float: left;
  margin-left: 30px;
  position: absolute;
}
.nav-logo img {
  max-width: 60px;
  margin-left: 60px;
}
.nav-links {
  float: right;
  width: 20%;
  margin: 0 5px;
  display: flex;
  justify-content: space-evenly;
  right: 0;
}
.nav-links li {
  list-style: none;
  margin-left: 15px;
}
.nav-links li:last-child {
  margin-right: 30px;
}
/*#endregion */

/*region Cart*/
.cart-panel {
  position: fixed;
  right: 0;
  top: 0;
  width: 100%;
  height: 100%;
}
.cart-panel > .inactive {
  width: 80%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.85);
}
.cart-panel > .cart {
  position: absolute;
  right: 0;
  width: 20%;
  height: 100%;
  background-color: white;
}
.cart-panel > .cart > div {
  padding: 16px;
  border-bottom: black solid 1px;
  width: 100%;
}
/*endregion*/
</style>