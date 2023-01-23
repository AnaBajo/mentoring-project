<template>
  <div class="text-center mt-3">

    <h1>Hours: {{ hours }}</h1>
    <h2>Minutes: {{ mins }}</h2>
    <h3>Seconds: {{ secs }}</h3>
    <p>Values sum: {{ sumTimeValues }}</p>
    <p>{{ date }}</p>
  </div>
</template>

<script>
  export default {
    name: 'ClockComponent',
    data() {
      return {
        hours: 0,
        mins: 0,
        secs: 0,
        date: new Date()
      }
    },
    computed: {
      sumTimeValues(){
        return this.hours + this.mins + this.secs
      }
    },
    mounted() {
      this.incrementSecs();
      this.incrementMins();
      this.incrementHours();
    },
    methods: {
      incrementSecs() {
        setInterval(() => {
          if(this.secs === 59) {
            this.secs = 0
          }
          this.secs++;
        }, 1000)
      },
      incrementMins(){
        setInterval(() => {
          if(this.mins === 59) {
            this.mins = 0
          }
          this.mins++;
        }, 60000)
      },
      incrementHours(){
        setInterval(() => {
          if(this.hours === 23) {
            this.hours = 0
          }
          this.hours++;
        }, 3600000)
      }
    }
  }
</script>