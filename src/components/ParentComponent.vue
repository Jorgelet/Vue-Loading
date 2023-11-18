<template>
    <img v-lazy="{ 
        src: lazyOptions.src, 
        lifecycle: lazyOptions.lifecycle,
        delay: lazyOptions.delay
    }" lazy="loading">

</template>

<script setup>
import { ref } from 'vue'
const lazyOptions = ref({
    src: 'https://picsum.photos/1200/800', 
    delay: 500,
    lifecycle: {
        loading: (el) =>{
            console.log('cargando imagen',el)
        },
        error: (el) =>{
            console.log("error en la carga",el)
        },
        loaded: (el) =>{
            console.log('imagen cargada',el)
        }
    }
})
</script>
