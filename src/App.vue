<template>
  <div id="app">
    <h1 class="title">Simple ToDo</h1>
    <Todo class="todo" />
  </div>
</template>

<script>
import Todo from "@/components/Todo";

export default {
  name: "App",

  components: {
    Todo,
  },
};
</script>

<style scoped>
#app {
  font-family: sans-serif;
  text-align: center;
  justify-content: center;
}

.title {
  color: #555555;
}

.todo {
  max-width: 600px;
  margin: auto;
}
</style>
