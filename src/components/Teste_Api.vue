<template>
   <div class="app">
    <h1>Gerenciador</h1>
      <div>
        <button @click="getUser">Api</button>
      </div>
  </div>
  </template>
  <script>
  import axios from "axios";

  export default {
   name: "app",
   emits: ["mostrar","esconder"],
   components: {

   },
   data() {
     return {
       user: {},
       show: false
     };
   },
   created() {
     this.getUser();
   },
   methods: {
     getUser() {
      this.$emit("mostrar",[])
       axios
         .get("https://servicodados.ibge.gov.br/api/v1/localidades/estados/")
         .then((res) => {
           this.user = res.data;
           this.$emit("esconder",[])
           console.log(res)
         })
         .catch((error) => {
           console.log(error);
         });
     },
   },
  };
  </script>

  <style>
  #pressao{
    background-color: rgba(0, 0, 0, 0.5);

  }
  </style>