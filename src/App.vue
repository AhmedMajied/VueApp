<template>
  <!-- place it outside app div -->
  <teleport to=".extra">
    <Child :arr="arr" :title="title" @close="custom">
      <!-- slot -->
      <h1>I am a slot</h1>

      <!-- named slot -->
      <template v-slot:links>
        <a href="#">link1</a>
      </template>
    </Child>
  </teleport>
</template>

<script>
import Child from "./components/child.vue";

export default {
  // name: 'App',
  components: {
    Child,
  },
  data() {
    return {
      arr: [],
      title: "Welcome to Your Vue.js App",
    };
  },
  mounted(){
    this.arr = ["name", "lool"]
  },
  methods: {
    custom() {
      alert("custom");
    },
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
