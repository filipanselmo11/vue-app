<template>
  <div id="app">
    <input type="text" v-model="text.question" />
    <span>Text: {{ text }}</span>
    <span>Api: {{ apiResponse }}</span>
  </div>
</template>

<script>
/*eslint-disable*/
export default {
  name: "App",
  data: () => ({
    text: {
      question: "",
    },
    // text: "",
    apiResponse: "Start",
  }),
  methods: {
    simulateApi(response, time) {
      return new Promise((res) => {
        setTimeout(() => {
          this.apiResponse = response;
          console.log("api promisse");
        }, 1000 * time);
      });
    },
    async fetchApi(value, time) {
      await this.simulateApi(value, time);
    },
    callApi(newValue, oldValue) {
      console.log(newValue, oldValue);
      this.fetchApi("Call", 1);
    },
  },
  watch: {
    "text.question"(val, old) {
      console.log(val, old);
    },
    // text: [
    //   "callApi",
    //   function handler2(val, old) {
    //     console.log(val, old);
    //     this.fetchApi("Handler 2", 2);
    //   },
    //   {
    //     handler: function handler3(val, old) {
    //       console.log(val, old);
    //       this.fetchApi("Handler 3", 3);
    //     },
    //   },
    // ],
    // text(newValue, oldValue) {},
    // text: "callApi",
    // text: {
    //   immediate: true,
    //   handler(newValue, oldValue) {
    //     this.fetchApi(Math.random());
    //   },
    // },
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
