<template>
  <div id="app">
    <button @click="fullNameComputed = 'Michael Morbius'">Click</button>
    <!-- <span>{{ fullName() }}</span>
    <span>{{ fullName() }}</span>
    <span>{{ fullNameComputed }}</span> -->
    <span>{{ fullNameComputed }}</span>
    <!-- {{ count }} -->
  </div>
</template>

<script>
export default {
  name: "App",
  data: () => ({
    count: 0,
    firstName: "Fílip",
    lastName: "Anselmo",
  }),
  computed: {
    fullNameComputed: {
      get() {
        return `${this.firstName} ${this.lastName}`;
      },
      set(value) {
        const [first, last ] = value.split(' ');
        this.firstName = first;
        this.lastName = last;

      },
      // return Math.random();
    },
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
