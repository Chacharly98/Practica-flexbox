<template>
  <div id="lista" class="w-1/2 min-h-screen h-full flex flex-col p-4">
    <div class="w-full h-auto">
      <p class="text-3xl text-purple-900 font-bold">
        Total de elementos
        <span class="font-bold">{{ total_unidad }}</span>
      </p>
    </div>
    <div class="w-full flex-1 relative">
      <div class="absolute inset-0 overflow-y-auto">
        <ul class="w-full h-auto mt-4">
          <li v-for="(item, index) in cart" :key="index" class="w-full h-auto flex justify-between">
            <span class="text-lg font-bold text-gray-600">{{ item.name }}</span>
            <span class="text-md">$ {{item.price}}</span>
          </li>
        </ul>
      </div>
    </div>
    <div class="w-full h-auto">
      <p class="text-3xl text-purple-900 font-bold">Total $ {{total_precio}}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ["cart"],
  name: "lista",
  computed: {
    total_unidad() {
      return this.cart.length;
    },
    total_precio() {
      let total = 0;
      for (const item of this.cart) {
        total += parseFloat(item.price);
      }
      return total;
    }
  }
};
</script>