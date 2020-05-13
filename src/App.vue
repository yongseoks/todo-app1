<template>
  <div>
    {{ msg }}
    <!-- <main v-if="show">메인</main> -->
    <todo-header></todo-header>
    <todo-input v-on:add="addItem"></todo-input>
    <todo-list v-bind:propsdata="todoItems"></todo-list>
    <todo-footer v-on:clear="clearItems"></todo-footer>
  </div>
</template>

<script>
import TodoHeader from "./components/TodoHeader.vue";
import TodoInput from "./components/TodoInput.vue";
import TodoList from "./components/TodoList.vue";
import TodoFooter from "@/components/TodoFooter.vue";

export default {
  components: {
    "todo-header": TodoHeader,
    "todo-input": TodoInput,
    "todo-list": TodoList,
    "todo-footer": TodoFooter
  },
  methods: {
    fetchTodoItems: function() {
      for (var i = 0; i < localStorage.length; i++) {
        var value = localStorage.key(i);
        this.todoItems.push(value);
      }
      //   return arr;
    }
  },
  clearItems: function() {
    this.todoItems = [];
    localStorage.clear();
  },
  addItem: function(todoItem) {
    this.todoItems.push(todoItem);
    localStorage.setItem(todoItem, todoItem);
  },
  removeItem: function() {},
  data() {
    return {
      todoItems: []
    };
  }
};
</script>

<style>
</style>