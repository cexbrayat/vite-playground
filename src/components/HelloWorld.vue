<template>
  <h1>{{ price }}</h1>
  <ul>
    <li v-for="(change, index) in history" :key="index">{{ change }}</li>
  </ul>
</template>

<script lang="ts">
import { defineComponent, ref, watchEffect } from 'vue'

export default defineComponent({
  name: 'User',
  setup() {
    const price = ref(10);

    const history = ref<Array<string>>([]);
    const stopRecording = watchEffect(() => {
      history.value.push(`Price changed to ${price.value}`);
    });

    // stop recording after 3 seconds
    setTimeout(() => {
      stopRecording();
    }, 3000);

    return { price, history };
  }
})
</script>
