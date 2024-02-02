<template>
  <HeaderVue 
  v-if="showHeader"
  />

  <div>
    Nome : {{ firstName }}<br/> 
    Sobrenome: {{ lastName }}
    <button v-on:click="onClick('Ola mundo')">
        Clique Para Alertar {{ nome }}
    </button>
    <input v-model="nome"/>
  </div>

  <img
    alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
  
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import HeaderVue from './components/Header.vue';
export default {
  name: 'App',
  components: {
    HelloWorld,
    HeaderVue
  },
  data(){
    return {
      firstName:'Joao',
      lastName:'Silva',
      showHeader:true,
      nome:''
    }
  },
  watch:{
    nome(newValue,OldValue){
      console.log(newValue,OldValue)
    }
  },
  methods:{
    onClick(text){
      alert(text)
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
