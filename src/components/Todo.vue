<template>
  <div class="todo">
    <div class="task-input">
      <TaskInput @addItem="onAddItem" />
    </div>

    <div class="task-list">
      <h4 class="title">タスク一覧</h4>
      <TaskList v-if="hasItem" :items="items" @deleteItem="onDeleteItem" />
      <span v-else class="message">タスクがありません</span>
    </div>
  </div>
</template>

<script>
import TaskInput from "./TaskInput/TaskInput";
import TaskList from "./TaskList/TaskList";

export default {
  name: "Todo",

  components: {
    TaskInput,
    TaskList,
  },

  data: () => ({
    nextId: 0,
    items: [],
  }),

  computed: {
    hasItem() {
      return this.items.length > 0;
    },
  },

  methods: {
    onAddItem(title) {
      const item = {
        id: this.nextId,
        title,
      };

      this.items.push(item);
      this.nextId += 1;
    },

    onDeleteItem(deleteItemId) {
      this.items = this.items.filter(({ id }) => id != deleteItemId);
    },
  },
};
</script>

<style scoped>
.title {
  color: #555555;
  margin-bottom: 0.5rem;
}

.message {
  color: orange;
}

.task-input,
.task-list {
  margin: 12px;
}
</style>
