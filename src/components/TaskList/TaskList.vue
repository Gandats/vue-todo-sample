<template>
  <ul class="list">
    <TaskListItem
      v-for="item in items"
      :key="item.id"
      :id="item.id"
      @deleteItem="onDeleteItem"
    >{{ item.title }}</TaskListItem>
  </ul>
</template>

<script>
import TaskListItem from "./TaskListItem";

export default {
  name: "TaskList",

  components: { TaskListItem },

  props: {
    items: {
      type: Array,
      required: true,
    },
  },

  methods: {
    onDeleteItem(id) {
      this.$emit("deleteItem", id);
    },
  },
};
</script>

<style scoped>
.list {
  text-align: start;
  list-style: none;
  padding-inline-start: 0;
}
</style>
