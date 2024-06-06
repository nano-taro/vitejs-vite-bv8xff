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

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  data() {
    return {
      red: 0,
      blue: 0,
      green: 0,
    };
  },

  methods: {
    next(answer: string) {
      if (answer === '赤') {
        this.red = this.red + 1;
      } else if (answer === '青') {
        this.blue = this.blue + 1;
      } else if (answer === '緑') {
        this.green = this.green + 1;
      }
    },

    reset() {
      this.red = 0;
      this.blue = 0;
      this.green = 0;
    },
  },
});
</script>
