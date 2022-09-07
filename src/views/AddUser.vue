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
                    <button type="submit" class="btn btn-success" @click="addUser()">submit</button>
                </div>
            </div>
            <div class="col-3"></div>
        </div>
    </div>
</template>


<script setup lang="ts">

import {useRouter } from "vue-router"
import UserService from '@/services/UserService.ts'
import { ref } from "@vue/reactivity"
let userDetails:any= []

const router = useRouter();
function addUser(){
    UserService.userDetails.push(userDetails)
    console.log(userDetails)
    window.alert('user successfully created')
     router.push('/')
}
</script>