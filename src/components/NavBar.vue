<template>
  <nav class="navbar bg-dark">
    <h2 class="mx-2">

      <span style="border-radius: 10px" class="mx-2 text-white badge bg-success">Vue App
      </span>
    </h2>
    <p class="text-white">welcome ! <strong>{{ name }}</strong></p>
    <ul class="p-0 m-0">
      <li style="list-style: none">
        <router-link to="/">
          <button class="me-2 btn btn-outline-light">HOME</button>
        </router-link>
        <router-link to="/create">
          <button class="me-2 btn btn-outline-light">CREATE</button>
        </router-link>
      </li>
    </ul>

  </nav>
  <prep>{{obj}}</prep>
  <button class="btn btn-secondary" @click="getMethod()">Alert</button>

  <button class="btn btn-secondary" @click="sendData(book)">send data to Parent</button>
</template>

<script setup lang="ts">
 var  book="Wings of Fire"

  const props = defineProps<{
  name: string
  count:number
  obj:object
  getMethod:Function
  sendData:Function
}>() 

// interface Pro {
//   name: string
//   count: number
// }


// const props = withDefaults(defineProps<{
//   name: string
//   count: number
// }>(), {
//   count: 3,
//   name:"venkatesh"
// })


</script>
<style>
</style>