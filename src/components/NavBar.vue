<template>
    <v-app-bar app color="black" dark flat class="px-12" >
      <v-btn >
        <img src="logo.png" alt="Logo" class="img-logo mr-2" height="200">
        
        <h2>LOREM </h2> 
        <h2 class="textipsum mr-10"> IPSUM</h2>
      </v-btn>
      
  
      <!-- <v-spacer></v-spacer> -->
      <v-btn text @click="scroll('lorem')" >LOREM</v-btn>
      <v-btn text @click="scroll('lorem')"  >LOREM</v-btn>
      <v-btn text @click="scroll('portfolio')"  >LOREMIPSUM</v-btn>
      <v-btn text @click="scroll('services')" > LOREM & IPSUM</v-btn>
      <v-btn text @click="scroll('page')"  > LOREM</v-btn>
    </v-app-bar>
  </template>
  
  <script>
  export default {
    methods: {
      scroll(refName) {
        const element = document.getElementById(refName);
        element.scrollIntoView({ behavior: "smooth" });
      },
    },
  };
  </script>
  
  <style>
.textipsum {
    color: #D9EF0C;
}
.img-logo{
    height: 40px;
}
  </style>