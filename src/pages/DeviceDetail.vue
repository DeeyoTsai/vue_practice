<script setup>
import { ref, onBeforeMount } from 'vue';
import { useRoute } from 'vue-router';

const storageKey = "auo-device-key";
const route = useRoute()
const deviceName = ref("");
const deviceId = ref("");

onBeforeMount(() => {
    const id = route.params.itemid;
    const allDevice = JSON.parse(localStorage.getItem(storageKey));
    const device = allDevice.find((d) => d.id === id);
    // console.log(device);
    deviceName.value = device.title;
    deviceId.value = device.id;
});

</script>

<template>

    <!-- <h1 class="h1">設備 : {{ $route.params.itemid }}</h1>  -->
    <h1 class="h1"> 設備:{{deviceName}} </h1> 
    <div> 編號:{{deviceId}} </div>      
    
</template>