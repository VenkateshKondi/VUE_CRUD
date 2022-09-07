<template>
  <div class="container">
    <h2> Opps! Page not found</h2>
    <input type="text" v-model="name.value">

    <h1>{{ name.value }}</h1>
    <h2>{{age}}</h2>
    <input type="text" :value="age">
    <button class="btn btn-info" @click="getLoaded()" >Loading</button>
    <div class="spinner-border m-5" role="status" v-if="name.isLoading">
      <span class="visually-hidden">Loading...</span>
    </div>
  </div>

</template>

<script setup lang="ts">import { reactive } from '@vue/reactivity';
var name = reactive({ value: "venkatesh" ,isLoading : false})
let age=22
function getLoaded(){
  debugger
  name.isLoading=!name.isLoading
}
</script>

<style scoped>
</style>