<template>
  <div id="app">
  <p>{{contador}}</p>
  <botao-incrementar
    @update:contador="contador = $event"
    :contador="contador"
  ></botao-incrementar>

  <!-- Faz a mesma coisa que o código acima -->
  <botao-incrementar :contador.sync="contador"></botao-incrementar>
</div>
</template>

<script>
const BotaoIncrementar = {
  props: ["contador"],
  template: `<button @click="incrementar">Emitir</button>`,
  data() {
    return {
      contadorComponente: this.contador
    };
  },
  methods: {
    incrementar() {
      this.contadorComponente++;
      this.$emit("update:contador", this.contadorComponente);
    }
  }
};

const vm = new Vue({
  el: "#app",
  data: {
    contador: 0
  },
  components: {
    BotaoIncrementar
  }
});
</script>

