<template>
  <div>
    <SalutationName
      v-model:salutation="form.salutation"
      v-model:name="form.name"
    />
    <pre>{{ form }}</pre>

    <br />

    <base-input v-model:modelValue="myInput" />
    <pre>
      {{ myInput }}
    </pre>
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
      form: {
        salutation: "",
        name: "",
      },
    });
    return { ...toRefs(state) };
  },
};
</script>
