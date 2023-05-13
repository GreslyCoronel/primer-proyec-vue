<script setup>

import { ref } from 'vue'
//const saludo = "Mañana sera"
//const complemento = ref(" cruel")

//complemento.value = " bonito"
const title = ref('Mega ejemplo')
const solicitudes = ref(0)
const incrementar = ()=>{
    solicitudes.value++
}
const decrementar = ()=>{
    if(solicitudes.value > 0){
    solicitudes.value--
    }
}
</script>

<template>
    <h2>{{ title }}</h2>
    <div class="user">
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
             <path stroke-linecap="round" stroke-linejoin="round" d="M17.982 18.725A7.488 7.488 0 0012 15.75a7.488 7.488 0 00-5.982 2.975m11.963 0a9 9 0 10-11.963 0m11.963 0A8.966 8.966 0 0112 21a8.966 8.966 0 01-5.982-2.275M15 9.75a3 3 0 11-6 0 3 3 0 016 0z" />
        </svg>
        <div v-if="solicitudes > 0" class="notification">
            {{ solicitudes }}
        </div>
    </div>
    <span @click="incrementar">
        +
    </span>
    <span @click="decrementar">
        -
    </span>
    <div v-show="solicitudes > 0">
        Tienes una solicitud de amistad
    </div>
    <input type="text" v-model="title">
</template>

<style scoped>
 .user {
  position: relative;
  width: 40px;
  height: 40px;
 
 }
 .notification{
    position: absolute;
    top: -12px;
    right: -12px;
    background-color: gray;
    color: white;
    text-align: center;
    border-radius: 50%;
    height: 24px;
    width: 24px;
 }
 span{
    background-color: plum;
    width: 32px;
    height: 32px;
    display: inline-block;
    text-align: center;
    margin: 10px;
    border-radius: 4px;
 }
 span:hover{
    background:rgb(196, 169, 196);
    cursor: pointer;
    
 }
</style>
