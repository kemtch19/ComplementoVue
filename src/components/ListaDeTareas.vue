<template>
  <div class="lista"> <!-- Todos los componentes deben de estar dentro de un div -->
    <h2>Lista de tareas</h2>
    <input type="text" v-model="nuevaTarea" @keyup.enter="addTarea"> <!-- con el v-model de manera bidireccional le indicamos a vue en que variable va a caer los datos que le mandamos, pero todo eso luego de subir una tecla, la cual en este caso es el enter -->
    <ul>
      <li v-for="(i, index) in tareas" :key="index"> <!-- con v-for iteramos sobre el array que es tareas (como si fuera un foreach), le damos un nombre al iterador que en este caso es i para posteriormente utilizarlo en el código y vue implemento que key lo que nos hace ver vue es que con index le vamos a dar una itereación única y vue identifique los valores de la lista (ej: 1, 2, 3, etc. ) y es mucho mejor cuando tengamos que añadir los elentos de la lista -->
        {{ i }} <!-- Imprimimos en la template lo que tenemos en el array todo recorrido -->
        <button @click="borrarTarea">Borrar</button>
      </li> 
    </ul>
  </div>
</template>

<script setup>

import {ref} from "vue"; /* iniciaremos atributos reactivos  */
const tareas = ref([]); /* Creamos un array donde estara metidas las tareas */
const nuevaTarea = ref(""); /* Almacenaremos lo que se traiga del input */

const addTarea=()=>{ /* vamos a hacer una función flecha para agregar las tareas abajo  */
  tareas.value.push(nuevaTarea.value); /* metemos en el array lo que traemos del input que son las tareas y estaba vacío y ahora lo empujamos al array */
  nuevaTarea.value = ""; /* Luego de que se empujo el valor dentro del array lo que hacemos es que limpiamos el valor de la variable */
}

const borrarTarea = (index) =>{
  tareas.value.splice(index, 1);
}


</script>

<style scoped>
</style>