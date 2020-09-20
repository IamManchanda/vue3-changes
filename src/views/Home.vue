<template>
  <div>
    <p>Salutation Name</p>
    <salutation-name
      v-model:salutation.capitalize="form.salutation"
      v-model:name.capitalize="form.name"
    />
    <pre>{{ form }}</pre>

    <br />
    <p>Base Input</p>
    <base-input
      v-model:modelValue="email"
      @blur="email = 'blurrr@its.cold'"
      label="Email:"
      type="email"
      class="thicc"
    />
    <pre>{{ email }}</pre>

    <br />

    <p>Input with lazy v-model modifier</p>
    <input type="text" v-model.lazy="message" />
    <pre>{{ message }}</pre>

    <br />

    <p>Input with number v-model modifier</p>
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
      form: {
        salutation: "",
        name: "",
      },
      email: "",
      message: "",
      number: "",
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
