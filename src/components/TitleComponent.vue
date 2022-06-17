<template>
  <h1>Vue JS</h1>
</template>

<script>
export default {
  name: "TitleComponent",
  data: () => ({
    hello: "Mundo",
  }),
  beforeDestroy(){
    console.log('Before Destroy')
    console.log(this.hello);
  },
  destroyed(){
    console.log('Destroy');
    console.log(this.hello);
  }
//   beforeCreate() {
//     console.log("Before Create");
//     console.log(this.hello);
//   },
//   created() {
//     console.log("Created app");
//     console.log(this.hello);
//     // Geralmente utilizado na chamada de API
//   },
//   beforeMount() {
//     console.log("Before Mount APp");
//     console.log(this.$el);
//   },
//   mounted() {
//     console.log("Mounted App");
//     console.log(this.$el);
//   },
};
</script>

<style></style>
