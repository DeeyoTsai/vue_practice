<script setup>
import { computed } from 'vue';
import { RouterLink } from 'vue-router';

const props = defineProps({
    it:{
        type:Object,
        require:true,
    },
});

const emits = defineEmits(["remove-auo-item"]);
const remove = () => {
    emits("remove-auo-item", props.it.id)
};

const url = computed(() => `/devices/${props.it.id}`);

</script>


<template>

<ul>
    <li class="list-style">
        <RouterLink :to="url" class="item"> {{ it.title }} </RouterLink>
        <button @click="remove" class="px-2 py-1 text-white bg-black"> X </button>
    </li>
</ul>        
    
</template>

<style scoped>
.list-style{
    @apply flex items-center justify-between px-2 py-1 my-1 text-lg bg-slate-100;
}
.item{
    @apply hover:bg-fuchsia-600
}
</style>
