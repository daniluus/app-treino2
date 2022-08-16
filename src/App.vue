<template>
  <div id="app">
    <header>
      <h1 @click="abaAtiva = 'TreinoA'">Treino <span>A</span></h1>
      <h1 @click="abaAtiva = 'TreinoB'">Treino <span>B</span></h1>
      <h1 @click="abaAtiva = 'TreinoC'">Treino <span>C</span></h1>
    </header>
        
    <keep-alive>
      <transition mode="out-in">
        <component :is="abaAtiva"></component>
      </transition>
    </keep-alive> 

        
  </div>
</template>

<script>
import TreinoA from './components/TreinoA.vue'
import TreinoB from './components/TreinoB.vue'
import TreinoC from './components/TreinoC.vue'

export default {
  name: 'App',
  data(){
    return{
      abaAtiva: "TreinoA",
          
    }
  },
  methods: {
    abrirModal(){      
    }
  },
  components: {
    TreinoA,
    TreinoB,    
    TreinoC
  }
}
</script>

<style>
.v-enter-active,
.v-leave-active {
  transition: all 1s;
}
.v-enter,
.v-leave-to {
  opacity: 0;
  transform: translate3d(0, -20px, 0);
}
</style>
