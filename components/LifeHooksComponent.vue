<template>
  <div class="text-center">
    <h1 v-if="showElement" class="m-5 text-center" ref="example-element" >{{ propertyComputed }}</h1>
    <button @click="showElement = !showElement" type="button" class="btn btn-primary m-2">toggle button</button>
    <p class="m-3">beforeUpdate(): {{ counter }}</p>
    <p>{{ deleteProperty }}</p>
  </div>
</template>
<script>
export default {
  data() {
    return {
      property: 'initial example property value',
      showElement: true,
      counter: 0,
      deleteProperty: 'remove me!'
    }
  },
  computed: {
    propertyComputed() {
      return this.property
    }
  },
  beforeCreate() {
    // At this point, events and lifecycle have been initialized.
    // console.log('beforeCreate() hook runs at the initialization of your component - data has not been made reactive, and events have not been set up yet')
  },
  created() {
    // At this point, this.property is now reactive and propertyComputed will update.
    // console.log('created() hook runs before the templates and Virtual DOM have been mounted or rendered - you are able to access reactive data and events that are active')
    this.property = 'data property updated in the created() hook'

    setInterval(() => {
      this.counter++
    }, 1000)
  },
  beforeMount() {
    // At this point, vm.$el has not been created yet.
    // console.log(`beforeMount() hook runs right before the initial render happens and after the template or render functions have been compiled`)
  },
  mounted() {
    // At this point, vm.$el has been created and el has been replaced.
    // console.log(`Use mounted() for modifying the DOM—particularly when integrating non-Vue libraries`);
    console.log(`this.$el.textContent: ${ this.$el.textContent}`) // Example component.
  },
  beforeUpdate() {
    // At this point, Virtual DOM has not re-rendered or patched yet.
    // console.log(`beforeUpdate() logs the counter value every second, before the DOM updates. `)
    // console.log(this.counter)
  },
  updated() {
    // Fired every second, should always be true
    // console.log(`At this point, Virtual DOM has re-rendered and patched.`)
    // console.log(+this.$refs['example-element'].textContent === this.counter)
  },
  beforeDestroy() {
    console.log(`At this point, watchers, child components, and event listeners have not been teared down yet.`)
    // Perform the teardown procedure for deleteProperty.
    // (In this case, effectively nothing)
    this.deleteProperty = null
    delete this.deleteProperty
  }
}
</script>
