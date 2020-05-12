<template>
  <div id="app" class="w-auto min-h-screen h-full flex px-6 overflow-hidden h-32">
    <div class="w-1/2 min-h-screen p-4 h-full ">
        <h1 class="italic font-serif text-5xl text-center text-purple-900 font-bold">Carrito de compras</h1>
        <input v-model="name" placeholder="producto" class="bg-purple-500 text-white rounded-full py-2 px-4" />
        <input v-model="price" class="bg-purple-500 text-white rounded-full py-2 px-4 " />
      <span v-if="'' != name && price > 0" class="inline-flex rounded-md shadow-sm mt-6">
        <button  @click="agregar" class="inline-flex rounded-full py-2 px-4 bg-purple-900 text-white">Agregar</button>
      </span>  
      <span v-else>
        <p class="text-xs mt-4 text-red-400">Escribir nombre y precio del producto</p>
      </span>
        <picture class="h-full w-auto overflow-hidden  flex justify-center ">
          <img src="/static/carros.jpg" width="500" height="500"/>
        </picture>  
    </div>
    <lista :cart="cart" />
  </div>
</template>

<script>
import lista from "./components/lista"

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
    },
  },
  components: {
    lista
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