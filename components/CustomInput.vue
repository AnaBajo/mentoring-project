<template>
  <div>
    <b-form-input :value="inputValue" type="text" class="justify-content-center" :placeholder="placeholderValue" v-model="inputValue"  />
    <!-- <b-form-input :value="inputValue" type="text" class="justify-content-center" :placeholder="placeholderValue" @keypress.native="collectInputValue"  /> -->
    <select name="" id="" v-model="selectValue">
      <option value="1">1</option>
      <option value="2">2</option>
      <option value="3">3</option>
    </select>
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
      inputValue: 0,
      selectValue: ''
    }
  },
  created() {
    this.$nuxt.$on('emitted-event', () => {
      console.log(this.inputValue);
      console.log(this.selectValue);
    })
  },
  methods: {
    collectInputValue(Event) {
      this.inputValue = Event.target.value
    },
  }
}
</script>

