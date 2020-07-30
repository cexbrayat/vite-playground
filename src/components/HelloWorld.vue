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
    watchEffect(() => {
      history.value.push(`Price changed to ${price.value}`);
    });

    return { price, history };
  }
})
</script>
