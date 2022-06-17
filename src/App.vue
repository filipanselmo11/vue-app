<template>
  <div id="app">
    <button>Click</button>
  </div>
</template>

<script>
export default {
  name: "App",
  data: () => ({
    count: {
      x: 0,
    },
  }),
  mounted() {
    // this.y = 0;
    // this.$set(this.count, "y", 1);
    this.count = { ...this.count, ...{ a: 1, b: 2 } };
  },
};
</script>

<style>
#app {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
}
</style>
