<template>
  <v-card
    class="mx-auto"
    max-width="1200"
    outlined
  >
    <v-card-title>
      Table Sample
      <v-spacer></v-spacer>
      <v-btn
        outlined
        large
        color="success"
        class="mr-4"
      >
        Submit
      </v-btn>
    </v-card-title>
    <v-row class="mx-auto">
      <v-col cols="3">
        <v-text-field
          v-model="search"
          append-icon="mdi-magnify"
          label="Search"
          outlined
          dense
          hide-details
        ></v-text-field>
      </v-col>
      <v-col cols="3">
        <v-select
          :items="status"
          v-model="selectStatus"
          label="Status"
          outlined
          dense
        ></v-select>
      </v-col>
      <v-col cols="3">
        <v-select
          :items="types"
          v-model="selectType"
          label="Type"
          outlined
          dense
        ></v-select>
      </v-col>
    </v-row>
    <v-data-table
      :headers="headers"
      :items="desserts"
      :search="search"
    ></v-data-table>
  </v-card>
</template>
<script>
  export default {
    layout: 'main',
    data () {
      return {
        search: '',
        selectStatus: null,
        status: [
          { text: 'All', value : null },
          { text: 'select 1', value : 'aa' },
          { text: 'select 2', value : 'bb' },
          { text: 'select 3', value : 'cc' },
          { text: 'select 4', value : 'dd' },
        ],
        selectType: null,
        types: [
          { text: 'All', value : null },
          { text: 'types 1', value : 'a' },
          { text: 'types 2', value : 'b' },
          { text: 'types 3', value : 'c' },
          { text: 'types 4', value : 'd' },
        ],
        headers: [
          {
            text: 'Dessert (100g serving)',
            align: 'start',
            sortable: false,
            value: 'name',
          },
          { text: 'Type', value: 'type' , filter: this.typesFilter },
          { text: 'Status', value: 'status', filter: this.statusFilter },
          { text: 'Carbs (g)', value: 'carbs' },
          { text: 'Protein (g)', value: 'protein' },
          { text: 'Iron (%)', value: 'iron' },
        ],
        desserts: [
          {
            name: 'Frozen Yogurt',
            type: 'c',
            status: 'aa',
            carbs: 24,
            protein: 4.0,
            iron: '1%',
          },
          {
            name: 'Ice cream sandwich',
            type: 'd',
            status: 'bb',
            carbs: 37,
            protein: 4.3,
            iron: '1%',
          },
          {
            name: 'Eclair',
            type: 'a',
            status: 'cc',
            carbs: 23,
            protein: 6.0,
            iron: '7%',
          },
          {
            name: 'Cupcake',
            type: 'a',
            status: 'dd',
            carbs: 67,
            protein: 4.3,
            iron: '8%',
          },
          {
            name: 'Gingerbread',
            type: 'b',
            status: 'aa',
            carbs: 49,
            protein: 3.9,
            iron: '16%',
          },
          {
            name: 'Jelly bean',
            type: 'a',
            status: 'bb',
            carbs: 94,
            protein: 0.0,
            iron: '0%',
          },
          {
            name: 'Lollipop',
            type: 'c',
            status: 'cc',
            carbs: 98,
            protein: 0,
            iron: '2%',
          },
          {
            name: 'Honeycomb',
            type: 'b',
            status: 'dd',
            carbs: 87,
            protein: 6.5,
            iron: '45%',
          },
          {
            name: 'Donut',
            type: 'd',
            status: 'aa',
            carbs: 51,
            protein: 4.9,
            iron: '22%',
          },
          {
            name: 'KitKat',
            type: 'd',
            status: 'bb',
            carbs: 65,
            protein: 7,
            iron: '6%',
          },
        ],
      }
    },
    methods: {
      statusFilter(value) {
        // If this filter has no value we just skip the entire filter.
        if (!this.selectStatus) {
          return true;
        }
        // Check if the current loop value (The calories value)
        // equals to the selected value at the <v-select>.
        return value === this.selectStatus;
      },
      typesFilter(value) {
        // If this filter has no value we just skip the entire filter.
        if (!this.selectType) {
          return true;
        }
        // Check if the current loop value (The calories value)
        // equals to the selected value at the <v-select>.
        return value === this.selectType;
      }
    }
  }
</script>
