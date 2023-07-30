<script setup>

  import {ref} from "vue";
  import RadioButton from "@/components/form/RadioButton.vue";

  const clientsToShow = ref("active")
  const radioGroupName = "clients-list"
  const checkBoxOptions = [
    {label: "Active", id: "active-clients", value: "active"},
    {label: "Inactive", id: "inactive-clients", value: "inactive"},
    {label: "All Clients", id: "all-clients", value: "all"}

  ]
</script>

<template>
  <h1>This is the list of all clients, sorted alphabetically</h1>
  <div class="control">
    <RadioButton
      v-for="option in checkBoxOptions"
      :key="option.value"
      :id="option.id"
      :value="option.value"
      :label="option.label"
      :name="radioGroupName"
      v-model="clientsToShow"
    />
  </div>

  <div v-if="clientsToShow == 'active'">Active Clients List</div>
  <div v-else-if="clientsToShow =='inactive'">Inactive Clients List</div>
  <div v-else-if="clientsToShow == 'all'">All Clients List</div>

</template>

<style scoped>

</style>