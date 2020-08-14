<template>
  <ButtonBase @click="$emit('click')">追加</ButtonBase>
</template>

<script>
import ButtonBase from "@/components/Base/ButtonBase";

export default {
  name: "AddButton",

  components: {
    ButtonBase,
  },
};
</script>
