<template>
    <div>
        <div :key="tache.id" v-for="tache in taches">
            <TacheDetail @toggle-reminder="$emit('toggle-reminder', tache.id)" @delete-tache="$emit('delete-tache', tache.id)" :tache="tache"/>
            
        </div>
    </div>
</template>

<script>
import TacheDetail from './TacheDetail';
export default {
    name: 'TacheTeste',
    props: {
        taches: Array
    },

    components: {
        TacheDetail,
    },
 
}
</script>