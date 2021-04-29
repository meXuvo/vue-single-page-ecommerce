<template>
  <header>
    <div
      class="w-full h-20 bg-gray-300 text-white flex justify-between flex-auto"
    >
      <div class="flex flex-auto justify-between items-center space-x-5">
        <button
          class="px-5 py-2 bg-blue-500 text-white rounded"
          @click="toggleClick()"
        >
          siderbar
        </button>
        <h1 class="uppercase text-3xl">logo</h1>
        <button class="px-5 py-2 text-gray-800 rounded" @click="cartToggle">
          cart
        </button>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "Appheader",
  props: {
    value: {
      type: Boolean,
      required: true,
    },
    cartValue: {
      type: Boolean,
      required: true,
    },
  },
  data() {
    return {
      toggleValue: this.value,
      cartToggledata: this.cartValue,
    };
  },
  methods: {
    toggleClick() {
      this.$emit(
        "bodyShapeChangeValue",
        (this.toggleValue = !this.toggleValue)
      );
    },
    cartToggle() {
      this.$emit("cart", (this.cartToggledata = !this.cartToggledata));
    },
  },
};
</script>

<style>
</style>