<template>
  <textarea v-model="localValue" v-on:keyup="resize" v-on:keydown="inputHandler" ></textarea>
</template>

<script>
import autosize from 'autosize'

export default {
  name: 'autoresize',
  props: ['value'],
  data: function () {
    return {
      localValue: this.value
    }
  },
  mounted () {
    autosize(this.$el)
  },
  methods: {
    resize: function(event) {
      autosize(event.target)
    },
    inputHandler: function(event) {
      if (event.keyCode === 13 && !event.shiftKey) {
        //console.log("enter key pressed")
        event.preventDefault();
        // sending Event data back to parent node
        this.$emit('onEnterKeydown', event)
      }
    }
  },
  watch: {
    value (newVal, oldVal) {
      if (newVal !== oldVal) {
        this.localValue = newVal
      }
    },
    localValue (newVal, oldVal) {
      if (newVal !== oldVal) {
        this.$emit('input', newVal)
      }
    }
  },
}
</script>

<style scoped>

</style>