<template>
  <button :disabled="disabled" @click="action">{{txt}}</button>
</template>

<script>
export default {
  props: {
    txt: String,
    disabled: Boolean,
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