<template>
  <div class="text-center">
    <!-- <b-button @click="incrementValue()" variant="primary" size="lg" class="m-5">{{ text }}</b-button> -->
    <b-button @click="emitCustomEvent" variant="primary" size="lg" class="m-5">{{ text }}</b-button>
  </div>
</template>

<script>
export default {
  name: 'CustomButton',
  props: {
    text: {
      type: String,
      required: true,
      default: "button text"
    }
  },
  mounted() {
    this.$emit('custom-event');
  },   
  methods: {
      emitCustomEvent(){
      this.$nuxt.$emit('emitted-event')
    }
  }
}
</script>