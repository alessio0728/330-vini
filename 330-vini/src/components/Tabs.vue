<script setup>

import { ref } from 'vue'

let tab = ref(0);



</script>



<!--Tabs per la navigazione-->

<template>

  <div class="w-full">

    <div class="flex justify-between p-5">

      <div 
      
      @click="tab=0"

      >

        <img class="imglogo" src="../media/logo.jpg" alt="logo" width="100">

      </div>

      
      <button

      @click="tab=1"

      :class="{'btn-neutral' : tab === 1}"
      
      class="btn btn-xs sm:btn+-sm md:btn-md lg:btn-lg ">

        HOME

      </button>

      <button

      @click="tab=2"

      :class="{'btn-neutral' : tab === 2}"
      
      class="btn btn-xs sm:btn+-sm md:btn-md lg:btn-lg ">

        PRODOTTI

      </button>

      <button

      @click="tab=3"

      :class="{'btn-neutral' : tab === 3}"
      
      class="btn btn-xs sm:btn+-sm md:btn-md lg:btn-lg ">

        PROPRIETARIO

      </button>

      <button

      @click="tab=4"

      :class="{'btn-neutral' : tab === 4}"
      
      class="btn btn-xs sm:btn+-sm md:btn-md lg:btn-lg ">

        GALLERIA

      </button>

      <button

      @click="tab=5"

      :class="{'btn-neutral' : tab === 5}"
      
      class="btn btn-xs sm:btn+-sm md:btn-md lg:btn-lg ">

        EVENTI

      </button>


    </div>

    <!--Contenuto-->

    <div>

      <div v-if="tab === 0" class="py-10 px-6">
        <img src="../media/" alt="">
      </div>

      <div v-if="tab === 1" class="py-10 px-6">
        <img src="../media/" alt="">
      </div>

      <div v-if="tab === 2"  class="py-10 px-6">
        <h1>contenuto 2 PRODOTTI</h1>
      </div>

      <div v-if="tab === 3"  class="py-10 px-6">
        <h1>contenuto 3 proprietario</h1>
      </div>

      <div v-if="tab === 4"  class="py-10 px-6">
        <h1>contenuto 4 galleria</h1>
      </div>

      <div v-if="tab === 5"  class="py-10 px-6">
        <h1>contenuto 6 eventi</h1>
      </div>

    </div>







  </div>


</template>

<style>



.imglogo {

  border-radius: 50%;
}







</style>