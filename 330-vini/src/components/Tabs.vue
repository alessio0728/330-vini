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

        <img src="../media/Petruzzelli.jpg" alt="logo" width="100">

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


    </div>

    <!--Contenuto-->

    <div>

      <div v-if="tab === 0" class="py-10 px-6">
        <img src="../media/Petruzzelli.jpg" alt="">
      </div>

      <div v-if="tab === 1" class="py-10 px-6">
        <img src="../media/Petruzzelli.jpg" alt="">
      </div>

      <div v-if="tab === 2"  class="py-10 px-6">
        <h1>contenuto 2</h1>
      </div>

    </div>







  </div>


</template>