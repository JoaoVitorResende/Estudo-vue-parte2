<template>
  <div id="app">
    <button v-on:click="alerta">alerta</button>
  </div>

  <div>
    <input type="text" id="msg" v-on:keydown="atualizavalor" />
    <br />
    <br />
    <p>{{ vl }}</p>
    <br />
    <br />
    <input type="text" id="txtmsg" v-on:keydown.enter="atualizavalor" />
    <br />
    <br />
    <p>{{ vl }}</p>
  </div>

  <div>
    <button v-on:click="incrementa1">1</button>
    {{ contador1 }}
    <br />
    <button v-on:click="incrementa2">2</button>
    {{ contador2 }}
    <br />
    <h1>antigo {{ antigo1 }}</h1>
    <br />
    <h1>novo {{ novo1 }}</h1>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      vl: 0,
      contador: 0,
      contador1: 0,
      contador2: 0,
      antigo1: 0,
      novo1: 0,
    };
  },
  watch: {
    contador1(novo, antigo) {
      this.antigo1 = antigo;
      this.novo1 = novo;
      if (novo == 10) {
        setTimeout(() => {
          this.contador1 = 0;
        }, 2000);
      }
    },
  },
  methods: {
    alerta() {
      alert(this.vl);
    },
    atualizavalor(e) {
      this.vl = e.target.value;
    },
    atualizavalorenter(e) {
      this.vl = e.target.value;
    },
    incrementa1() {
      this.contador1++;
    },
    incrementa2() {
      this.contador2++;
    },
  },
};
</script>



<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
