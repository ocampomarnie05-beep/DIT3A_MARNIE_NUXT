<template>
  <v-card
    title="Nutrition"
    flat
  >
    <template v-slot:text>
      <v-text-field
        v-model="search"
        label="Search"
        prepend-inner-icon="mdi-magnify"
        variant="outlined"
        hide-details
        single-line
      ></v-text-field>
    </template>

    <v-data-table
      :headers="headers"
      :items="desserts"
      :search="search"
    ></v-data-table>
  </v-card>
</template>
<script setup>
  import { ref } from 'vue'
    const { data: inventory } = await useFetch ('https://localhost:1337/api/inventories');
  const search = ref('')
  const headers = [

    { key: 'product_name', title: 'Product' },
    { key: 'product_description', title: 'Description' },
    { key: 'Quantity', title: 'Quantity'},
    { key: 'protein', title: 'Protein (g)' },
    { key: 'iron', title: 'Iron (%)' },
  ]

</script>