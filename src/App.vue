<script setup lang="ts">
import { ref } from "@vue/reactivity";
import { RouterLink, RouterView } from "vue-router";
import NavBar from "./components/NavBar.vue";
import UserTable from "./components/UserTable.vue";

components:UserTable

var userName="venki"
var count=0
var obj={
    age:22,
    cost:30
}
var bookName=ref("")
function getAlert(){
  window.alert("this is from App.vue")
}

function getBook(e){
 
  
   bookName.value=e
   console.log(bookName)
   debugger
}
</script >

<template>
  <NavBar :name="userName" :count="count" :obj="obj" :getMethod="getAlert" :sendData="getBook"/>
<p>Book from child: <strong>{{bookName}}</strong></p>

  <RouterView/>
</template>