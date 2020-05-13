<template>
  <button v-on:click="clearTodoItems">Clear</button>
</template>

<script>
export default {
  methods: {
    clearTodoItems() {
      this.$emit("clear");
    }
  }
};
</script>

