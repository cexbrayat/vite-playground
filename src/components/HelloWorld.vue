<template>
  <h1>{{ counter }}</h1>
</template>

<script lang="ts">
import { defineComponent, toRefs, watchEffect } from 'vue'

export default defineComponent({
  name: 'HelloWorld',
  props: {
    counter: Number
  },
  setup(props) {
    const { counter } = toRefs(props);
    watchEffect(() => {
      console.log('The new counter value is: ' + counter.value)
    })
  }
})
</script>
