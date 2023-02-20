<template>
  <div>
    <b-container class="p-5 text-center">
      <custom-input  placeholder-value="type a number"   />
      <custom-button text="Submit" @custom-event="showInputValue" />
    </b-container>
  </div>
</template>
<script>
export default {
  methods: {
    showInputValue() {
      console.log('should show input value');
    },
  }
}
</script>
