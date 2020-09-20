<template>
  <label>{{ label }}</label>
  <input
    v-bind="{
      ...$attrs,
      onInput: event => $emit('update:modelValue', event.target.value),
    }"
    :value="modelValue"
  />
</template>

<script>
import { reactive, toRefs } from "vue";

export default {
  props: {
    modelValue: {
      type: [String, Number],
      default: "",
    },
    label: {
      type: String,
      default: null,
    },
  },
  setup() {
    const state = reactive({});
    return { ...toRefs(state) };
  },
};
</script>

<style lang="scss" scoped>
input {
  width: 50%;
}
</style>
