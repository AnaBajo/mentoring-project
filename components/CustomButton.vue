<template>
  <div class="text-center">
    <b-button @click="incrementValue()" variant="primary" size="lg" class="m-5">{{ text }}</b-button>
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
  methods: {
    incrementValue() {
      this.$nuxt.$emit('clicked', this.inputValue)
      console.log(this.inputValue)
    },
  }
}
</script>