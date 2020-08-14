<!-- タスク追加のコンポーネント -->
<template>
  <div>
    <input
      placeholder="CDを返す"
      v-model="title"
      @compositionstart="isComposition=true"
      @compositionend="isComposition=false"
      @keydown.enter="addItem"
    />

    <AddButton class="add-button" @click="addItem" />
  </div>
</template>

<script>
import AddButton from "./AddButton";

export default {
  name: "TaskInput",

  components: {
    AddButton,
  },

  data: () => ({
    title: "",
    isComposition: false,
  }),

  methods: {
    addItem() {
      if (this.isComposition) return; // IMEの変換中
      if (this.title === "") return;

      this.$emit("addItem", this.title);
      this.title = "";
    },
  },
};
</script>

<style scoped>
div {
  display: flex;
  text-align: center;
}

input {
  flex: 1;
}

.add-button {
  margin-left: 0.4rem;
}
</style>
