<script setup>
const widthInit = Math.round(Math.random() * 10);
const heightInit = Math.round(Math.random() * 10);
const width = ref(widthInit);
const height = ref(heightInit);


const reactive = reactive({
  width: widthInit,
  height: heightInit
})

const area2 = computed(() => {
  return reactive.width * reactive.height;
})
// ref属性を使った実装
const area = () => {
  return width.value * height.value;
};

setInterval(() => {
  width.value = Math.round(Math.random() * 10);
  height.value = Math.round(Math.random() * 10);
}, 1000)
</script>
<template>
  <p>縦 {{ height }} 横 {{ width }} の面積は {{ area() }}です。</p>
  <p>
    縦 {{ reactive.height }} 横 {{ reactive.width }} の面積は {{ area() }}です。
  </p>
  <div>
    <NuxtRouteAnnouncer />
    <NuxtWelcome />
  </div>
</template>
