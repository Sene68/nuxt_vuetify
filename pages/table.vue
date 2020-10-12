<template>
  <v-main>
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
          <v-combobox
            :items="status"
            label="Status"
            outlined
            dense
          ></v-combobox>
        </v-col>
        <v-col cols="3">
          <v-combobox
            :items="types"
            label="Type"
            outlined
            dense
          ></v-combobox>
        </v-col>
      </v-row>
      <v-data-table
        :headers="headers"
        :items="desserts"
        :search="search"
      ></v-data-table>
    </v-card>
  </v-main>
</template>
<script>
  export default {
    data () {
      return {
        search: '',
        selectStatus: 'select 1',
        status: [
          'select 1',
          'select 2',
          'select 3',
          'select 4',
        ],
        selectType: 'types 1',
        types: [
          'types 1',
          'types 2',
          'types 3',
          'types 4',
        ],
        headers: [
          {
            text: 'Dessert (100g serving)',
            align: 'start',
            sortable: false,
            value: 'name',
          },
          { text: 'Calories', value: 'calories' },
          { text: 'Fat (g)', value: 'fat' },
          { text: 'Carbs (g)', value: 'carbs' },
          { text: 'Protein (g)', value: 'protein' },
          { text: 'Iron (%)', value: 'iron' },
        ],
        desserts: [
          {
            name: 'Frozen Yogurt',
            calories: 159,
            fat: 6.0,
            carbs: 24,
            protein: 4.0,
            iron: '1%',
          },
          {
            name: 'Ice cream sandwich',
            calories: 237,
            fat: 9.0,
            carbs: 37,
            protein: 4.3,
            iron: '1%',
          },
          {
            name: 'Eclair',
            calories: 262,
            fat: 16.0,
            carbs: 23,
            protein: 6.0,
            iron: '7%',
          },
          {
            name: 'Cupcake',
            calories: 305,
            fat: 3.7,
            carbs: 67,
            protein: 4.3,
            iron: '8%',
          },
          {
            name: 'Gingerbread',
            calories: 356,
            fat: 16.0,
            carbs: 49,
            protein: 3.9,
            iron: '16%',
          },
          {
            name: 'Jelly bean',
            calories: 375,
            fat: 0.0,
            carbs: 94,
            protein: 0.0,
            iron: '0%',
          },
          {
            name: 'Lollipop',
            calories: 392,
            fat: 0.2,
            carbs: 98,
            protein: 0,
            iron: '2%',
          },
          {
            name: 'Honeycomb',
            calories: 408,
            fat: 3.2,
            carbs: 87,
            protein: 6.5,
            iron: '45%',
          },
          {
            name: 'Donut',
            calories: 452,
            fat: 25.0,
            carbs: 51,
            protein: 4.9,
            iron: '22%',
          },
          {
            name: 'KitKat',
            calories: 518,
            fat: 26.0,
            carbs: 65,
            protein: 7,
            iron: '6%',
          },
        ],
      }
    },
  }
</script>
