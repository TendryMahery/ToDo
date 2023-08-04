<template>
 <div class="border border-gray-500 p-4">
   
    <h1>add tache</h1>
    <form @submit="onSubmit" action="">
    <div class="flex flex-col">
        
        <label for="prenom">prenom</label>
        <input type="text" v-model="prenom" name="prenom" class="border border-gray-700 p-1" placeholder="prenom">
        <label for="text">text</label>
        <input type="text" v-model="text" name="text" class="border border-gray-700 p-1" placeholder="text">
        <label for="reminder">reminder</label>
        <input type="checkbox" v-model="reminder" name="reminder" id="" class="mb-4">
        <button class="bg-blue-400 p-2 rounded-md focus:bg-blue-600 duration-75">add tache</button>
        
    </div>
    </form>
 </div>
</template>

<script>
export default {
    name: 'AddTache',
    data() {
        return {
            prenom: '',
            text: '',
            reminder: false
        }
    },
    methods: {
        onSubmit(e) {
            e.preventDefault();
            
            if (!this.text) {
                alert('remplit le formulaire stp')
            }

            const newTache = {
                id: Math.floor(Math.random() * 100),
                prenom: this.prenom,
                text: this.text,
                reminder: this.reminder

            }

            this.prenom = '',
            this.text = '',
            this.reminder = false

            this.$emit('add-tache', newTache)        
            
        }
        
    }
}
</script>

