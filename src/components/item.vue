<script setup>

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

</script>


<template>

<ul>
    <li class="list-style">{{ it.title }}</li>
    <button @click="remove" 
            class="px-2 py-1 text-white bg-black"
    > X </button>
</ul>        
    
</template>

<style scoped>
.list-style{
    @apply flex items-center justify-between px-2 py-1 my-1 text-lg bg-slate-100;
}
</style>
