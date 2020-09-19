<template>
  <div>
    <base-input v-model:modelValue="myInput" />
    {{ myInput }}
  </div>
</template>

<script>
import { reactive, toRefs } from "vue";
import BaseInput from "@/components/ui/base-input";

export default {
  components: {
    BaseInput,
  },
  setup() {
    const state = reactive({
      myInput: "",
    });
    return { ...toRefs(state) };
  },
};
</script>
