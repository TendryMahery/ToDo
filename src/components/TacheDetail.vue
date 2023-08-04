<template>
    <div class="bg-gray-300 mb-2 flex justify-between">
        <div>
           <button @dblclick="$emit('toggle-reminder', tache.id)" :class="[tache.reminder ? 'text-green-500 text-3xl' : 'text-red-500 text-2xl', 'tache']"> <i class="fas fa-check-circle" ></i></button>
        <h1 class="text-gray-500">{{ tache.prenom }}</h1>
        <h1 class="text-gray-500 text-sm">_{{ tache.text }}</h1>
        
        </div>
        <button @click="$emit('delete-tache', tache.id)"><i class="fas fa-times mr-6 mt-6"></i></button>
        
    </div>
    
</template>

<script>
export default {
    name:'TacheDetail',

    props: {
        tache: Object,
    },

}
</script>

<style scoped>

</style>