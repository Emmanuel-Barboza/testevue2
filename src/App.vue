<template>
  <div>
    <div v-show="show" id="pressao">
    </div>
    <Teste_Api v-on:mostrar="show = true" v-on:esconder="show = false"/>
  </div>
</template>

<script>
import Teste_Api from "./components/Teste_Api";

  export default{
    name: 'app',
    data() {
     return {
       show: false,
     };
   },
    components:{
    Teste_Api
},
    methods:{
      teste(){
        alert("af")
      }
    }

  }
</script>

<style>
  #pressao{
    background-color: rgba(0, 0, 0, 0.5);
    position: fixed;
    width: 100%;
    height: 100vh;
  }
</style>