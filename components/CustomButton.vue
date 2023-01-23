<template>
  <div class="text-center">
    <b-button variant="primary" size="lg" class="m-5">{{ text }}</b-button>
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
  }
}
</script>