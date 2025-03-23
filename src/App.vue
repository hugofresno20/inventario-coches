<template>
  <div>
    <h1>Tienda Reactiva 🛍️</h1>
    <div v-for="(producto, index) in productos" :key="index" style="margin-bottom: 1rem;">
      <h3>{{ producto.nombre }}</h3>
      <p>Precio: ${{ producto.precio }}</p>
      <p>Stock: {{ producto.stock }}</p>
      <p>Disponible: <strong :style="{ color: producto.disponible ? 'green' : 'red' }">{{ producto.disponible ? 'Sí' : 'No' }}</strong></p>

      <button @click="incrementarStock(index)">➕ Aumentar stock</button>
      <button @click="reducirStock(index)" :disabled="producto.stock === 0">➖ Reducir stock</button>
    </div>
  </div>
</template>

<script setup>
import { reactive, watch } from 'vue'

const productos = reactive([
  { nombre: 'Ferrari', precio: 500000, stock: 2, disponible: true },
  { nombre: 'Mercedes', precio: 120000, stock: 7, disponible: true },
  { nombre: 'BMW', precio: 100000, stock: 6, disponible: true }
])


</script>

<style scoped>
button {
  margin-right: 0.5rem;
}
</style>
