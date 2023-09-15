<script>
export default {
    props:{
        it:{
            type:Object,
            require:true,
        },
    },
    methods:{
        remove(){
            this.$emit('remove-auo-item', this.it.id);
        },
    },
};
</script>


<template>

<ul>
    <li>{{ it.title }}</li>
    <button @click="remove" 
            class="bg-black text-white px-2 py-1"
    > X </button>
</ul>        
    
</template>

<style scoped>

</style>
