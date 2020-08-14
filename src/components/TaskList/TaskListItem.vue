<template>
  <li class="list-item">
    <span class="list-item-title">
      <slot></slot>
    </span>

    <DeleteButton class="delete-button" @click="onDeleteButtonClick" />
  </li>
</template>


<script>
import DeleteButton from "./DeleteButton";
export default {
  name: "TaskListItem",

  components: {
    DeleteButton,
  },

  props: {
    id: {
      type: Number,
      require: true,
    },
  },

  methods: {
    onDeleteButtonClick() {
      this.$emit("deleteItem", this.id);
    },
  },
};
</script>

<style scoped>
.list-item {
  display: flex;
  background: skyblue;
  padding: 0.5rem 1rem;
  margin: 0.25rem 0;
  border-radius: 0.7rem;
}

.list-item-title {
  font-weight: bold;
  flex: 1;
}

.delete-button {
  margin-left: 0.2rem;
}
</style>
