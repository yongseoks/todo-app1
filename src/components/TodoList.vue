<template>
  <ul>
    <li v-for="(todoItems, index) in propsdata" v-bind:key="index"></li>
    {{ todoItems }}
    <button v-on:click="removeItems(todoItems, index)">remove</button>
  </ul>
</template>

<script>
export default {
  props: ["propsdata"],
  methods: {
    removeItems: function(todoItem, index) {
      console.log("clicked", todoItem, index);
      this.todoItems.splice(index, 1);
      //브라우저 저장소에서 삭제
      localStorage.removeItem(todoItem);
    }
  }
};
</script>
<style>
</style>