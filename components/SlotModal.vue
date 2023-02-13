<template>

    <b-modal id="modal-1" title="BootstrapVueModal">
      <!-- <p class="my-4">Hello from modal!</p> -->
      <slot name="content"/>
      <slot name="more-content" />
    </b-modal>

</template>
<script>
export default {
  mounted() {
    this.$bvModal.show("modal-1")
  }
}
</script>