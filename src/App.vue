<template>
<div id="app">
  <h1>Tienda 32 Bites</h1>
  <h3>Lista de juegos</h3>
  <table border="1px">
    <thead>
      <th>Código</th>
      <th>Nombre</th>
      <th>Stock</th>
      <th>Precio</th>
      <th>Acciones</th>
    </thead>
    <tbody>
      <tr v-for="(juego, i) in juegos" :key="i">
             
        <td>{{ juego.codigo }}</td>
        <td>{{ juego.nombre }}</td>
        <td>{{ juego.stock }}</td>
        <td>${{ Number(juego.precio).toLocaleString() }}</td>
        <td>
          <button @click="incrementar(i)" >+</button>
          <button @click="decrementar(i)" >-</button>
        </td>
      </tr>
    </tbody>
  </table>
  </div>
</template>

<script>

import { mapActions, mapState } from 'vuex'

export default {
  name: 'App',
  components: {
  },
  computed:{
    ...mapState(["juegos"])
  },
  methods: {
    ...mapActions(["incrementar", "decrementar"])
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

table {
  width: 50%;
  margin: auto;
}
</style>
