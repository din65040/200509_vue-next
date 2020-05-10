<template>
  <div id="app">
    <h1>Vue 3.0 Composition API</h1>
    <button @click="increment">Click</button>
    <p>count: {{ count }}</p>
    <p>doubleCount: {{ doubleCount }}</p>
  </div>
</template>

<script>
import { ref, computed } from "@vue/composition-api";

export default {
  setup() {
    const { count, increment, doubleCount } = useIncrementNumber();

    return {
      count,
      increment,
      doubleCount
    }
  },
};

const useIncrementNumber = () => {
  // data での定義
  let count = ref(0);

  // methods での定義
  const increment = () => {
    count.value += 1;
  };

  // computed での定義
  const doubleCount = computed(() => {
    return count.value * 2;
  });

  return {
    count,
    increment,
    doubleCount,
  };
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  border: 3px solid #2c3e50;
}
</style>
