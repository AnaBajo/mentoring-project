<template>
  <div>
    <h1 class="m-5 text-center" >{{ propertyComputed }}</h1>
  </div>
</template>
<script>
export default {
  data() {
    return {
      property: 'Example property.'
    }
  },
  computed: {
    propertyComputed() {
      return this.property
    }
  },
  beforeCreate() {
    // The beforeCreate hook runs at the initialization of your component - data has not been made reactive, and events have not been set up yet:
    console.log('At this point, events and lifecycle have been initialized.')
  },
  created() {
    // The created hook runs before the templates and Virtual DOM have been mounted or rendered - you are able to access reactive data and events that are active:
    console.log('At this point, this.property is now reactive and propertyComputed will update.')
    this.property = 'Example property updated.'
  },
  beforeMount() {
    // The beforeMount hook runs right before the initial render happens and after the template or render functions have been compiled:
    console.log(`At this point, vm.$el has not been created yet.`)
  },
  mounted() {
    // Use mounted for modifying the DOM—particularly when integrating non-Vue libraries:
    console.log(`At this point, vm.$el has been created and el has been replaced.`);
    console.log(this.$el.textContent) // Example component.
  }
}
</script>
