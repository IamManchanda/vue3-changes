<template>
  <div>
    <SalutationName
      v-model:salutation.capitalize="form.salutation"
      v-model:name.capitalize="form.name"
    />
    <pre>{{ form }}</pre>

    <br />

    <base-input v-model:modelValue="myInput" />
    <pre>{{ myInput }}</pre>

    <br />

    <input type="text" v-model.lazy="message" />
    <pre>{{ message }}</pre>

    <br />

    <input type="number" v-model.number="number" />
    <pre>{{ number }}</pre>
  </div>
</template>

<script>
import { reactive, toRefs } from "vue";
import BaseInput from "@/components/ui/base-input";
import SalutationName from "@/components/SalutationName";

export default {
  components: {
    BaseInput,
    SalutationName,
  },
  setup() {
    const state = reactive({
      myInput: "",
      message: "",
      number: "",
      form: {
        salutation: "",
        name: "",
      },
    });
    return { ...toRefs(state) };
  },
};
</script>

<style lang="scss" scoped>
input {
  width: 50%;
}
</style>
