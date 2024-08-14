<template>
  <h1>Hola Mundo desde el app</h1>
  <p>{{ contador }}</p>
  <button @click="Incrementar">Incrementar</button>
  <button @click="decrementar">Decrementar</button>
</template>

<script setup>
/* La etiqueta de script lleva setup para escribir código en composition api */
import { ref } from "vue"; /* recordar que ref es una función que se utiliza para crear una referencia  reactiva  a un valor para poder, en este caso podemos crear variables reactivas  */
const contador = ref(1);

/* Función para incrementar la variable */
const Incrementar = () => {
  contador.value++;
};

const decrementar = () => {
  contador.value--;
};
</script>

<style scoped>
p {
  background-color: red;
}
</style>