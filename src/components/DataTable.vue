<template>
<v-container >
      <v-row
      class="mb-6"
      no-gutters
    >
      <v-col cols="5">
        <v-sheet class="pa-2 ma-2">
        <p class="font-weight-black" style="float:'left'">Master Data Users</p>

        </v-sheet>
      </v-col>
      <v-col
        cols="2"
        offset="5"
      >
        <v-sheet class="pa-2 ma-2">
          <v-btn
          
          color="success"
          size="small"
          @click="this.$router.push({path: '/'})"
        >
          <v-icon icon="mdi-logout"></v-icon>
        </v-btn>
        </v-sheet>
      </v-col>
    </v-row>
    </v-container>
  <v-data-table
    v-model:page="page"
    :headers="headers"
    :items="desserts"
    :items-per-page="itemsPerPage"
    hide-default-footer
    class="elevation-1"
  >
    <template v-slot:bottom>
      <div class="text-center pt-2">
        <v-pagination
          v-model="page"
          :length="pageCount"
        ></v-pagination>
        <v-text-field
          :model-value="itemsPerPage"
          class="pa-2"
          label="Items per page"
          type="number"
          min="-1"
          max="15"
          hide-details
          @update:model-value="itemsPerPage = parseInt($event, 10)"
        ></v-text-field>
      </div>
    </template>
  </v-data-table>
</template>

<script setup>
  import { VDataTable } from 'vuetify/labs/VDataTable'
</script>
<script>
  export default {
    data () {
      return {
        page: 1,
        itemsPerPage: 5,
        headers: [
          {
            align: 'start',
            key: 'name',
            sortable: false,
            title: 'Name',
          },
          { title: 'Age', key: 'age' },
          { title: 'Address', key: 'address' },
          { title: 'Email', key: 'email' },
          { title: 'Phone No.', key: 'phone' },
        ],
        desserts: [
          {
            name: 'Admin',
            age: 20,
            address: 'Jl. Setiabudi 1',
            email: 'admin@gmail.com',
            phone: '08123456789',
          },
          {
            name: 'Super Admin',
            age: 24,
            address: 'Jl. Budi 1',
            email: 'superadmin@gmail.com',
            phone: '08123456789',
          },{
            name: 'Admin 2',
            age: 25,
            address: 'Jl. abc 1',
            email: 'admin2@gmail.com',
            phone: '08123456789',
          },{
            name: 'Adi',
            age: 26,
            address: 'Jl. jjj 1',
            email: 'adi@gmail.com',
            phone: '08123456789',
          },{
            name: 'Amat',
            age: 31,
            address: 'Jl. Serpong Raya',
            email: 'amat@gmail.com',
            phone: '08123456789',
          },{
            name: 'Bernard',
            age: 28,
            address: 'Jl. Kemanggisan',
            email: 'bernard@gmail.com',
            phone: '08123456789',
          },{
            name: 'Charly',
            age: 22,
            address: 'Jl. Grogol Utara 1',
            email: 'charly@gmail.com',
            phone: '08123456789',
          },{
            name: 'David',
            age: 21,
            address: 'Jl. Kemandoran 1',
            email: 'david@gmail.com',
            phone: '08123456789',
          },{
            name: 'Anroni',
            age: 28,
            address: 'Jl. Kebon mangga',
            email: 'admin@gmail.com',
            phone: '08123456789',
          },{
            name: 'dhani',
            age: 45,
            address: 'Jl. petamburan 1',
            email: 'dhani@gmail.com',
            phone: '08123456789',
          },
        ],
      }
    },
    computed: {
      pageCount () {
        return Math.ceil(this.desserts.length / this.itemsPerPage)
      },
    },
  }
</script>