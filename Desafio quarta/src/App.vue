<template>
  <div id="app">
    <header>

      <h1>Bem vindo !</h1>

    </header>

    <body>

    <label for="nome"> Ponha seu nome:</label>
    <br>
    <br>
    <input type="text" id="txtmsg" v-model="nome">
    <br>
    <br>
    <label for="idade"> Ponha sua idade:</label>
    <br>
    <br>
    <input type="text" id="txtmsg" v-model="idade">
    <br>
    <p> Seu nome é {{nome}} !! com idade de {{idade}}</p>
    <br>
    <br>
    <p>sua idade multiplica por três é {{idade*3}}</p>
    <br>
    <br>
    <p>numero aleatorio {{Math.floor(Math.random() * 10)}}</p>
    <br>
    <br>
    <label for="link"> Ponha um link:</label>
    <br>
    <input type="text" id="txtmsg" v-model="link">
    <br>
    <br>
    <img v-bind:src="link" width="600" height="600"/>
    <br>
    <br>
    <p>{{contador}}</p>
    <br>
    <br>
    <button v-on:click="somar">incrementa ai </button>
    <br>
    <br>
    <input type="text" id="txtmsg" v-model="vl1">
    <br>
    <br>
    <input type="text" id="txtmsg" v-model="vl2">
    <br>
    <button v-on:click="soma">soma </button>
    <br>
    <br>
    <p>soma é equivalente a {{r}}</p>
    <br>
    <br>
    <h1 v-on:mousemove="atualizarXY">
      posição X:{{x}}
      <br>
      posição Y:{{y}}
    </h1>
    </body>
    
  </div>
</template>

<script>
  export default{
    data:function(){
      return{
          nome:"",
          idade:"",
          link:'',
          contador:0,
          vl1:0,
          vl2:0,
          r:0,
          x:0,
          y:0
      }  
    },
    methods:{
      somar(){
        this.contador++
      },
      soma(){
        this.r = parseInt(this.vl1)+parseInt(this.vl2);
      },
      atualizarXY(e){
          this.x = e.clientX;
          this.y = e.clientY;
      }
    }
  }
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
