<template>
  <HelloWorld :counter="counter"/>
  <button @click="counter++">Click</button>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'
import HelloWorld from './components/HelloWorld.vue'

export default defineComponent({
  name: 'App',
  components: {
    HelloWorld
  },
  setup() {
    const counter = ref(0);
    return { counter };
  }
})
</script>
