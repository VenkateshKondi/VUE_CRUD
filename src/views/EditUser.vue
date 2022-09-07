<template>
    <div class="container">
        <div class="row">
            <div class="col-3"></div>

            <div class=" col-6 m-4 shadow-lg" >
                    <div class="mb-3">
                    <label class="form-label" for="inputEmail">ID</label>
                    <input type="email" class="form-control" placeholder="Enter ID" v-model="userDetails.id">
                </div>
                <div class="mb-3">
                    <label class="form-label" for="inputPassword">Name</label>
                    <input class="form-control" placeholder="Enter Name" v-model="userDetails.name">
                </div>
                <div class="mb-3">
                    <label class="form-label" for="inputPassword">Short Name</label>
                    <input class="form-control" placeholder="Enter Short Name" v-model="userDetails.shortName">
                </div>
                <div class="mb-3">
                    <button type="submit" class="btn btn-success" @click="update()">submit</button>
                </div>
            </div>
            <div class="col-3"></div>
        </div>
    </div>
</template>


<script setup lang="ts">
import { useRoute, useRouter } from "vue-router"
import UserService from '@/services/UserService.ts'
import { ref } from "@vue/reactivity"
import { onMounted } from "vue";
let userDetails = ref([])
let apiData:UserService = []

apiData = UserService.getData() 

const route = useRoute();
const router = useRouter();

let id=route.params.id

userDetails =getById(id)

function getById(id:any){
    return apiData[findIndex(id)]
   
}
function findIndex(id:any){
   return apiData.findIndex((x: any) => x.id == id)
}

function update(){
    
  router.push('/')
}
</script>