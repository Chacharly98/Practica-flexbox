<template>
  <div id="app" class="w-full min-h-screen  flex px-6 t">
    <div class="w-1/2 min-h-screen p-4 ">
        <h1 class="italic font-serif text-5xl text-center text-purple-900 font-bold">Carrito de compras</h1>
        <input v-model="name" placeholder="producto" class="bg-purple-200 font-bold rounded-l-lg px-2 py-2" />
        <input v-model="price" class="bg-purple-200 font-bold rounded-r-lg px-2 py-2" />
      <span v-if="'' != name && price > 0" class="inline-flex rounded-md shadow-sm mt-6">
        <button  @click="agregar" class="inline-flex rounded-full py-2 px-4 bg-purple-900 text-white">Agregar</button>
      </span>  
      <span v-else>
        <p class="text-lg mt-4 text-red-400 font-bold">Escribir nombre y precio del producto</p>
      </span>
        <picture class=" overflow-hidden  flex justify-center rounded-">
          <img src="/static/compras.png" width="500" height="500"/>
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