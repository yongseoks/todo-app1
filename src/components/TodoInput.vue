<template>
  <div>
    <input type="text" v-model="inputText" />
    <button v-on="addItem">add</button>
  </div>
</template>

<script>
export default {
  methods: {
    addItem: function() {
      this.$emit("add", this.inputText);
      localStorage.setItem(this.inputText, this.inputText);
      this.inputText = "";
      this.clearInut();
    }
  },
  data() {
    return {
      inputText: ""
    };
  }
};
</script>

<style>
</style>