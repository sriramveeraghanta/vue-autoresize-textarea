<template>
  <textarea v-model="localValue" v-on:keyup="resize"></textarea>
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