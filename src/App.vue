<template>
  <div>
    <Appheader
      :value="PersonValue"
      @bodyShapeChangeValue="PersonValue1"
      :cartValue="cartParent"
      @cart="parentView"
    />
    <div class="flex">
      <app-sider-bar v-if="PersonValue" class="bg-white flex-shrink-0 w-64" />
      <AppBody />
      <Cart v-if="cartParent" class="bg-white flex-shrink-0 w-64" />
    </div>
  </div>
</template>
<script>
//import ProductList from "./components/ProductList";
import Appheader from "./components/Appheader";
import AppBody from "./components/AppBody";
import AppSiderBar from "./components/AppSiderBar.vue";
import Cart from "./components/Cart";

export default {
  name: "App",
  components: {
    //ProductList
    Appheader,
    AppBody,
    AppSiderBar,
    Cart,
  },
  data() {
    return {
      infoName: "",
      info: null,
      name: "",
      PersonValue: false,
      cartParent: false,
    };
  },
  methods: {
    PersonValue1(value) {
      this.PersonValue = value;
    },
    parentView(value) {
      this.cartParent = value;
    },
  },
};
</script>

<style>
</style>
