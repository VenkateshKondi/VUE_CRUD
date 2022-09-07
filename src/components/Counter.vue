<template>
  <div class="container">
    <div class="shadow-lg">
      <h1>  {{count}}</h1>
      <!-- <input type="text" v-model="count"> -->
      <!-- <button class="btn btn-info" @click="count++">Increment</button>
      <button class="btn btn-warning" @click="count--">Decrement</button> -->
      <button class="btn btn-info" @click="inc()">Increment</button>
      <button class="btn btn-warning" @click="dec()">Decrement</button>
    </div>
    
  </div>
</template>
<script  setup lang="ts">
// export default {
//   data(){
//     return {
//         count:2
//     }
//   }

import { ref } from "@vue/reactivity"

// }
let count=ref(4)
function inc(){
    count.value++
}
function dec(){
    count.value--
}
</script>
<style>
  
</style>