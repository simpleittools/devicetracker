<script setup>

  import {ref} from "vue";
  import RadioButton from "@/components/form/RadioButton.vue";
  import InputForm from "@/components/form/InputForm.vue";

  const clientSearch = ref('')

  const clientsToShow = ref("active")
  const radioGroupName = "clients-list"
  const checkBoxOptions = [
    {label: "Active", id: "active-clients", value: "active"},
    {label: "Inactive", id: "inactive-clients", value: "inactive"},
    {label: "All Clients", id: "all-clients", value: "all"}

  ]


</script>

<template>
  <div class="container">
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

    <div v-if="clientsToShow === 'active'">Active Clients List</div>
    <div v-else-if="clientsToShow ==='inactive'">Inactive Clients List</div>
    <div v-else-if="clientsToShow === 'all'">All Clients List</div>

    <div class="columns">
      <div class="column is-9">
        <InputForm
          v-model="clientSearch"
          type="text"
          name="client-search"
          id="client-search"
          label="Search Client"
        />
      </div>
      <div class="column is-3">
        <button class="button is-primary">Search</button>
      </div>
    </div>
  </div>
</template>

<style scoped>

</style>