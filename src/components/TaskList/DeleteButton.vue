<template>
  <ButtonBase @click="$emit('click')">削除</ButtonBase>
</template>

<script>
import ButtonBase from "@/components/Base/ButtonBase";

export default {
  name: "DeleteButton",

  components: {
    ButtonBase,
  },
};
</script>
