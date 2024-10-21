<template>
    <div class="flex flex-col items-center justify-center h-screen">
      <div class="mb-8">
        <img class="degustazione" src="../media/degustazione31102024.jpg" alt="degustazione" width="500px">
      </div>
      
      <div class="grid auto-cols-max grid-flow-col gap-5 text-center mb-8">
        <div class="bg-neutral rounded-box text-neutral-content flex flex-col p-2">
          <span class="countdown font-mono text-5xl">
            <span :style="`--value:${days};`"></span>
          </span>
          Giorni
        </div>
        <div class="bg-neutral rounded-box text-neutral-content flex flex-col p-2">
          <span class="countdown font-mono text-5xl">
            <span :style="`--value:${hours};`"></span>
          </span>
          Ore
        </div>
        <div class="bg-neutral rounded-box text-neutral-content flex flex-col p-2">
          <span class="countdown font-mono text-5xl">
            <span :style="`--value:${minutes};`"></span>
          </span>
          Minuti
        </div>
        <div class="bg-neutral rounded-box text-neutral-content flex flex-col p-2">
          <span class="countdown font-mono text-5xl">
            <span :style="`--value:${seconds};`"></span>
          </span>
          Secondi
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        days: 0,
        hours: 0,
        minutes: 0,
        seconds: 0,
        countdownInterval: null
      };
    },
    mounted() {
      this.startCountdown();
    },
    beforeUnmount() {
      clearInterval(this.countdownInterval);
    },
    methods: {
      startCountdown() {
        const targetDate = new Date('2024-10-31T20:30:00Z'); // Mercoledì 31 Ottobre 2024, ore 20:30 UTC
        this.countdownInterval = setInterval(() => {
          const now = new Date();
          const diff = targetDate - now;
  
          if (diff <= 0) {
            clearInterval(this.countdownInterval);
            this.days = 0;
            this.hours = 0;
            this.minutes = 0;
            this.seconds = 0;
            alert('Countdown finished!');
            return;
          }
  
          this.days = Math.floor(diff / (1000 * 60 * 60 * 24));
          this.hours = Math.floor((diff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
          this.minutes = Math.floor((diff % (1000 * 60 * 60)) / (1000 * 60));
          this.seconds = Math.floor((diff % (1000 * 60)) / 1000);
        }, 1000);
      }
    }
  };
  </script>
  
  <style scoped>
  .countdown span {
    display: inline-block;
    min-width: 1em;
  }
  
  .grid.auto-cols-max.grid-flow-col.gap-5.text-center.mb-8 {
    margin-bottom: 250px;
  }
  </style>
  