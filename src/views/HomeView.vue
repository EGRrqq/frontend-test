<template>
  <main>
    <FormBuilder :configData="cfgData" />
  </main>
</template>

<script setup>
import FormBuilder from '../components/FormBuilder.vue'

import { ref } from 'vue';

const data = {
  buh1: {
    items: [
      { type: "input", label: "name" },
      { type: "select", label: "gender" },
      { type: "radio", label: "age" }
    ]
  },
  buh2: {
    items: [
      { type: "input", label: "name" },
      { type: "password", label: "type pass" },
      { type: "password", label: "repeat pass" }
    ]
  }
}

const cfgData = ref(data);
</script>
