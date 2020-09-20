<template>
  <button @click="action">{{txt}}</button>
</template>

<script>
export default {
  props: {
    txt: String,
  },
  methods: {
    action() {
      this.$emit("action");
    },
  },
};
</script>

<style>
</style>