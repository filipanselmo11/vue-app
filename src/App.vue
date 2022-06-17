<template>
  <div id="app">
    <title-component v-if="shouldAppear"></title-component>
    <button @click="shouldAppear = false">Click</button>
    {{ count }}
  </div>
</template>

<script>
import TitleComponent from "./components/TitleComponent.vue";
export default {
  name: "App",
  components: {
    TitleComponent,
  },
  data: () => ({
    count: 0,
    shouldAppear: true,
  }),
  beforeUpdate() {
    console.log("Before Update");
    console.log(this.count);
  },
  updated() {
    console.log("Updated");
    console.log(this.count);
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
