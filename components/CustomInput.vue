<template>
  <div>
    <b-form-input type="text" class="justify-content-center" :placeholder="placeholderValue" />
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
  }
}
</script>