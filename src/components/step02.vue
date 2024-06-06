<script setup lang="ts">
import { ref } from 'vue';

const red = ref(0);
const blue = ref(0);
const green = ref(0);

const next = (answer: string) => {
  if (answer === '赤') {
    red.value++;
  } else if (answer === '青') {
    blue.value++;
  } else if (answer === '緑') {
    green.value++;
  }
};

const reset = () => {
  red.value = 0;
  blue.value = 0;
  green.value = 0;
};
</script>

<template>
  <div>
    <h2>あなたの好きな色は？</h2>
    <button @click="next('赤')">赤</button>
    <button @click="next('青')">青</button>
    <button @click="next('緑')">緑</button>
    <h2>集計結果</h2>
    <p>赤：{{ red }}　青：{{ blue }}　緑：{{ green }}</p>
    <button @click="reset()">リセット</button>
  </div>
</template>
