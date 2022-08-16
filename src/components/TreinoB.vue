<template>
  <div>

    <section class="content">
      <p>Normal</p>
      <section class="galeria-treino">
        <div class="item-treino" v-for="i in 5" :key="i">
        <div v-for="{superior} in treino" :key="superior.id">
          <p>{{superior[i].id}}</p>
          <h3>{{superior[i].name}}</h3>
          <ul>
            <li>
              <img src="" alt="">
              <p>{{superior[i].config}}</p>
            </li>
            <li>
              <img src="" alt="">
              <p>3x12</p>
            </li>
            <li>
              <img src="" alt="">
              <p>{{superior[i].weight}}</p>
            </li>
          </ul>
        </div>
        <button class="botao" @click="modal = true">REST</button>
        </div>
      </section>
    </section>

    <section class="content">
      <p>Conjugado</p>
      <section class="galeria-treino">
        <div class="item-treino" v-for="j in 3" :key="j">
          <div v-for="{conjugado} in treino" :key="conjugado.id"> 
            <p>{{conjugado[j].id}}</p>
            <h3>{{conjugado[j].name}}</h3>
            <ul>
              <li>
                <img src="" alt="">
                <p>{{conjugado[j].config}}</p>
              </li>
              <li>
                <img src="" alt="">
                <p>3x12</p>
              </li>
              <li>
                <img src="" alt="">
                <p>{{conjugado[j].weight}}</p>
              </li>
            </ul>
          </div>
          <button class="botao" @click="modal = true">REST</button>
        </div>
      </section>
    </section>  
    
    <rest-modal 
      v-if="modal"
      :modal.sync="modal"
    ></rest-modal>
  </div>
</template>

<script>
import treinoB from '../../api/treinoB.json';
import RestModal from './RestModal.vue';

export default {
  name: 'TreinoB',
  data() {
    return {
      treino: treinoB,
      modal: false    
    }
  },
  components: {
    RestModal
  }
}
</script>

<style>

</style>
