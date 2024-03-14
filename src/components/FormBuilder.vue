<template>
  <div class="form-builder">
    <form @submit.prevent="onSubmit">
      <div v-for="(item, index) in items" :key="index">
        <component :is="getComponentName(item.type)" :label="item.label" />
      </div>

      <button type="submit">Отправить</button>
      <button type="reset">Стереть</button>
    </form>
  </div>
</template>

<script>
import FormInput from "@/components/form-items/FormInput.vue";
import FormSelect from "@/components/form-items/FormSelect.vue";
import FormRadio from "@/components/form-items/FormRadio.vue";
import FormPassword from "@/components/form-items/FormPassword.vue";

export default {
  name: "FormBuilder",

  // test data
  // iterate over config data later
  data() {
    return {
      items: [
        { type: "input", label: "name" },
        { type: "select", label: "gender" },
        { type: "radio", label: "age" },
        { type: "password", label: "type pass" }
      ]
    };
  },

  methods: {
    onSubmit() {
      alert("Submit");
    },

    // violates open closed principle
    // should find a better way to do this
    getComponentName(type) {
      switch (type) {
        case "input":
          return "FormInput";
        case "select":
          return "FormSelect";
        case "radio":
          return "FormRadio";
        case "radio":
          return "FormRadio";
        case "password":
          return "FormPassword";
        default:
          return "input";
      }
    },
  },
  components: { FormPassword, FormRadio, FormSelect, FormInput },
};
</script>

<style scoped></style>
