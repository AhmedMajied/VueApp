<template>
  <div class="title" @click.self="customeEvent">{{title}}</div>

  <ul>
    <li v-for="item in arr" :key="item">{{item}}</li>
  </ul>

  <slot>place holder when there is no slot</slot>

  <slot name="links"></slot>
</template>

<script>
export default {
  props: ["title", "arr"],
  methods: {
    customeEvent() {
      this.$emit("close");
    },
  },
};
</script>

<style scoped>
.title {
  color: red;
}
</style>