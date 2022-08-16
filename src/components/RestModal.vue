<template>
  <div>
    <section class="modal-container" data-modal="container">
    <button class="fechar-modal terminar" @click="fecharModal">X</button>

    <h1>titulo treino</h1>

    <div class="cronometro-series">
      <div class="item-cronometro">
        <p>CRONOMÊTRO</p>
        <span @click="iniciar">00:{{second}}</span>        
      </div>
      <div class="item-series">
        <p>SERIES</p>
        <span @click="somaSerie">{{serie}} of 3</span>
      </div>
    </div>

    <button class="botao" @click="fecharModal">TERMINAR</button>    
  </section>
  </div>
</template>

<script>

export default {
  name: 'RestModal',
  props: ["modal"],
  data(){
    return {
      timer: 30,      
      serie: 1,
      modalComponent: this.modal,
      teste: 30,
      millisecond: 0,
      second: 0,      
      cron: 0
    }
  },
  methods: {    
    tempo() {
      //incrementa os segundos
       this.second++;
      if( this.second==30){           
        //Zerar os  this.second
          this.second=0;
          clearInterval(this.cron);
      }     
    }, 
    iniciar() {      
        this.cron = setInterval(() => this.tempo(),1000)      
    },   
    somaSerie(){
      this.serie++;
      if(this.serie > 3){
        this.serie = 1;
      }
    },
    fecharModal(){
      this.modalComponent = false;
      this.$emit("update:modal", this.modalComponent)
    }
  },
}
</script>
