<template>
  <input
    :value="modelValue"
    type="text"
    @input="$emit('update:modelValue', $event.target.value)"
  />
</template>

<script>
export default {
  props: {
    modelValue: {
      type: [String, Number],
      default: "",
    },
  },
  setup() {
    return {};
  },
};
</script>

<style lang="scss" scoped>
input {
  width: 50%;
}
</style>
