<template>
  <div id="app">
    <h1 class="italic font-serif text-6xl text-center text-purple-900 font-bold">Carrito de compras </h1>
    <br />
    <br />
    <label class="italic font-serif text-4xl text-purple-900">Total de elementos: {{total_unidad}}</label>
    <br />
    <label class="italic font-serif text-4xl text-purple-900">Total: {{total_precio}}</label>
    <br />
    <br />
    <input v-model="name" class="bg-purple-500 text-white rounded-full py-2 px-4" />
    <br />
    <br />
    <label>{{toLower}}</label>
    <br />
    <br />
    <input v-model="price" class="bg-purple-500 text-white rounded-full py-2 px-4" />
    <br />
    <br />
    <button @click="agregar" class="rounded-full py-2 px-4 bg-purple-900 text-white">Agregar</button>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      cart: [],
      name: "",
      price: 0
    };
  },
  methods: {
    agregar() {
      this.cart.push({
        name: this.name,
        price: this.price
      });
      this.name = "";
      this.price = 0;
      console.log(this.cart);
    }
  },

  computed: {
    total_unidad() {
      return this.cart.length;
    },
    toLower() {
      return this.name.toLowerCase();
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

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>