<template>
  <div id="app">
    <div class="p-12 border-3-solid">
      <HeaderTeste @toggle-add-tache="toggleAddTache" :showAddTache="showAddTache" />
      <transition name="fade">
       <div>
          <AddTache v-show="showAddTache" @add-tache="addTache" />
        </div>
      </transition>
      
      <TacheTeste @toggle-reminder="toggleReminder" @delete-tache="deleteTache" :taches="taches"/>
    </div>  
  </div>
</template>

<script>
import './index.css';
import HeaderTeste from './components/HeaderTeste';
import TacheTeste from './components/TacheTeste';
import AddTache from './components/AddTache.vue'
export default {
  name: 'App',
  components: {
    HeaderTeste,
    TacheTeste,
    AddTache
  },

  data() {
    return {
      taches: [],
      showAddTache: true
    }
  },
  methods: {
    toggleAddTache() {
     this.showAddTache = !this.showAddTache 
    },

    addTache(tache) {
      this.taches = [...this.taches, tache]
    },

    deleteTache(id) {
      if (confirm("tu es sur de toi")) {
        this.taches = this.taches.filter((tache) => tache.id !== id)
      }
    },

    toggleReminder(id) {
    this.taches = this.taches.map((tache) => tache.id === id ? {...tache, reminder: !tache.reminder}: tache) 
   } 
  },

  created() {
    this.taches = [
      {
        id: 1,
        prenom: "tendry mahery",
        text: "developpeur full stack mern",
        reminder:true
      },
       {
        id: 2,
        prenom: "jean",
         text: "Docteur en informatique au sein de l'institut",
        reminder: false
      },
       {
        id: 3,
        prenom: "koto",
         text: "blablablablablablablablabal",
        reminder: false
      },
       {
        id: 4,
        prenom: "paul",
        text: "bloblbobloblobloblbobloblo",
        reminder: true
      },
    ]
  }
  
}
</script>


<style >
.fade-enter-active,
.fade-leave-active {
  transition: opacity .5s;
}

.fade-enter,
.fade-leave-active {
  opacity: 0;
  transform: translateX(20px);
}
</style>
