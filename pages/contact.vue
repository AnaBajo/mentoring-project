<template>
  <div>
    <b-container class="p-5 text-center">
      <custom-input  placeholder-value="type a number" @keypress.native="collectInputValue"  />
      <custom-button text="Submit" @click.native="emitCustomEvent" @custom-event="showInputValue" />
    </b-container>
  </div>
</template>
<script>
export default {
  methods: {
    collectInputValue(Event) {
      const inputvalue = Event.target.value
      console.log(inputvalue);
    },
    showInputValue() {
      console.log('should show input value');
    }
  }
}
</script>
