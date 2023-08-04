<template>
    <div class="flex space-x-12">
        <h1 class="text-2xl font-bold">task tracer</h1>
       <ButtonTeste  @toggle-add-tache="$emit('toggle-add-tache')" :text="showAddTache ? 'Clause' : 'add tache'" />
    </div>
</template>

<script>
import ButtonTeste from './ButtonTeste';
export default {
    name: 'HeaderTeste',
    props: {
        title: String,
        showAddTache: Boolean
    },

    components: {
        ButtonTeste,
    }
 
}
</script>