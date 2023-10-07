<template>
  <v-container fluid>
    <DataTableVue/>
  </v-container>
</template>

<script>
import DataTableVue from '@/components/DataTable.vue'


export default {
  name: 'DataTable',
  components: {
    DataTableVue
  }
}
</script>
