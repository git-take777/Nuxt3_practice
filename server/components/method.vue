<template>
  <p>{{ msg }}</p>
  <button @click="onButtonClick('Hello', $event)">こんにちは</button>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const msg = ref("まだ");
const onButtonClick = (label: string, event: Event): void => {
const target = event.target as HTMLButtonElement;
const text = target.innerText;
console.log(label, text);
}
msg.value = `${label} と ${text}`
</script>

<style scoped></style>
