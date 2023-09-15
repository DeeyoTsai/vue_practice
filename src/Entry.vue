<script setup>
import { RouterView, RouterLink } from "vue-router";


</script>

<template>
    <nav>
        <ul>
            <li><RouterLink to="/">設備管理系統</RouterLink> </li>
            <li><RouterLink to="/about"> 關於 </RouterLink></li>
            <li><RouterLink to="/app"> APP </RouterLink></li>
        </ul>
    </nav> 
    <main class="mx-6 sm:mx-16">
        <RouterView></RouterView>
    </main>
    
</template>