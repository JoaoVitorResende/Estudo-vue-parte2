<template>
  <div id="app">

    <h1 v-once>{{mensagem}}</h1>
    <h1>{{bemvindo()}}</h1>

    <input type="text" id="txtmsg" v-model="mensagem">{{mensagem}}
    <a v-bind:href="link">testelink</a>

  </div>
</template>

<script>
  export default{
    data:function(){
      return{
          mensagem: "olá mundo",
          link: "https://www.youtube.com/watch?v=dQw4w9WgXcQ"
      }  
    },
    methods:{
      bemvindo: function(){
        this.mensagem ="bem vindo (a)"
        return this.mensagem
      }
    }
  }
</script>

<style>
  #app{
    background-color: green;
    color: white;
  }
</style>
