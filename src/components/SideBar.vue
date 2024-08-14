<template>
  <div class="sidebar"> <!-- Nuevo Componente -->
    <h2>Barra lateral</h2>
    <router-link to="./contador">Contador</router-link>
    <!-- esta etiqueta solamente me ayuda para utilizar las rutas y debemos de tener instalado router -->
    <router-link to="./lista">Lista de tareas</router-link>
    <!-- esta etiqueta solamente me ayuda para utilizar las rutas y debemos de tener instalado router -->
  </div>
</template>

<script setup>
</script>

<style>
.sidebar {
  width: 200px;
  background-color: #fff;
}
</style>