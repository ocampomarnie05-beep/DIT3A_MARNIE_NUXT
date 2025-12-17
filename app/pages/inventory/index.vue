<template>
  <v-card
    title="Inventory"
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
      :items="inventory.data"
      :search="search"
    ></v-data-table>
  </v-card>
</template>
<script setup>
 const { data: inventory} = await useFetch('http://localhost:1337/api/inventories');

  const search = ref('')
  const headers = [
   
    { key: 'item_id', title: 'Item_id' },
    { key: 'product_name', title: 'Product_name' },
    { key: 'product_description', title: 'Description' },
    { key: 'quantity', title: 'Quantity' },
    { key: 'unit', title: 'Unit' },
    { key: 'condition', title: 'Condition' },
    { key: 'location', title: 'Location' },
    { key: 'acquisition_date', title: 'Acquisition_Date' },
  ]
  
  
</script>