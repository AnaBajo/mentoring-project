<template>
  <div class="container">
      <h1 ref="title1" class="mt-4 text-center" @dblclick="handleDoubleClicked">Title</h1>
      <!-- <custom-input  placeholder-value="logging every keydown..." @keydown="handleKeyDown"/> -->
      <div class="input">
        <input type="text" class="w-100" @keypress="handleKeyPress" />
      </div>
      <p class="w-100">{{ keystroke }}</p>
    <nuxt-link to="/contact" >
    <nuxt-link to="/nicolascage">Nicolas Cage</nuxt-link>
      <!-- <clock-component /> -->
      <custom-button text="Contact" />
    </nuxt-link>
    <custom-button text="Events" @click.native="handleComponentClick" @custom-event="handleCustomEvent"/>
    <!-- <slot-modal>
      <template #content>
        <span><p class="my-4">modal content</p></span> 
      </template>
      <template #more-content>
         <span><h3>some more modal content</h3></span>
      </template>
    </slot-modal> -->
  </div>
</template>
<script>
export default {
  name: 'IndexPage',
  watch: {
    // whenever question changes, this function will run
    question(newQuestion, oldQuestion) {
      if (newQuestion.includes('?')) {
        this.getAnswer()
      }
    }
  },
  methods: {
    handleDoubleClicked() {
      alert('Title is double-clicked')
    },
    handleKeyPress(event){
      // alert(`Im typing ${event.target.value}`)
      // console.log(event.target.value);
      const keystroke = event.target.value
      console.log(keystroke);
    },
    handleComponentClick(){
      alert('I need a modifier to be interactive')
    },
    handleCustomEvent(){
      // alert('Coming from the custom event')  
    }
  }
}
</script>

