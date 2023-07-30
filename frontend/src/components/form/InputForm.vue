<script setup>
import {ref, defineProps, watch, defineEmits} from 'vue'
const props = defineProps([
  "inputType",
  "name",
  "id",
  "inputClass",
  "modelValue",
  "label",
  "labelClass"
])
const inputModel = ref(props.modelValue)
const emit = defineEmits()

watch(() => props.modelValue, (newValue) => {
  inputModel.value = newValue
})

watch(inputModel, (newValue) => {
  emit('update:modelValue', newValue)
})
</script>

<template>
  <div class="field is-horizontal">
    <div class="field-label is-normal">
      <label
        :for="id"
        class="label"
        :class="labelClass"
      >
        {{label}}
      </label>
    </div>
    <div class="field-body">
      <div class="field">
        <div class="control">
          <input
            :type="inputType"
            :name="name"
            :id="id"
            class="input"
            :class="inputClass"
            v-bind="$attrs"
            v-model="inputModel"
          >
        </div>
      </div>
    </div>

  </div>

</template>

<style scoped>

</style>