<template>
  <div>
    <b-form-input :value="value" type="text" class="justify-content-center" :placeholder="placeholderValue"/>
  </div>
</template>

<script>
export default {
  name: 'CustomInput',
  props: {
    placeholderValue: {
      type: String,
      required: true,
      default: "placeholder text"
    }
  },
  data(){
    return {
      value: 0
    }
  },
  mounted() {
    this.$nuxt.$on('clicked', (data) => {
      this.value++
    })
  }
}
</script>

