<template>
  <h1>Bonjour {{ firstName.toUpperCase() }}</h1>
  <h2>Mon compte est à : {{ count }}</h2>
  <p>Je fais du vue.js</p>
  <div v-show="count>=5">Bravo vous avez cliqué plus de 5 fois</div>
  <button @click="increment">Increment</button>
  <button @click="decrement">Decrement</button>
</template>

<script setup>
import {ref} from 'vue'
const firstName = "Edouard"

const count = ref(0)
//Quand on crée une référence,ça crée un objet particulier avec une propriété value qui permet d'n modifier la valeur

console.log(count , count.value)

console.log(count)
//count.value = 3
// setInterval(()=>{
//   count.value++
// }, 1000)

const decrement = ()=>{
  count.value--
}

const increment = ()=>{
  count.value++

}
</script>



<style>
h1{color : red;}
p{color: blue;}
</style>
