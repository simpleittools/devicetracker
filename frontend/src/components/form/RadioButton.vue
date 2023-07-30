<script setup>
import {ref, defineProps, defineEmits} from "vue";

  const props = defineProps([
    "id",
    "value",
    "name",
    "label"
  ])

  const selectedModel = ref(null)

  const emit = defineEmits()

  function handleChange(event) {
    selectedModel.value = event.target.value;
    const newValue = event.target.value
    emit('update:modelValue', newValue)
  }

</script>

<template>
  <label
    class="radio"
    :for="id"
  >
    <input
      type="radio"
      :id="id"
      :name="name"
      :value="value"
      v-model="selectedModel"
      @change="handleChange"
      >
    {{ label }}
  </label>
</template>

<style scoped>

</style>