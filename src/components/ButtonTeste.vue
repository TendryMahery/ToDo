<template>
    <div>
        <button class="bg-blue-500 p-2 rounded-md" @click="onClick()">{{ text }}</button>
    </div>
</template>

<script>
export default {
    name: 'ButtonTeste',
    props: {
        text: String,
        showAddTache: Boolean
    },

    methods: {
        onClick() {
            this.$emit('toggle-add-tache')
        }
    },
}
</script>