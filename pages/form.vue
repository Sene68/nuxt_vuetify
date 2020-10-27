<template>
  <v-card
    class="mx-auto"
    max-width="500"
    outlined
  >
    <v-card-title>
      Form Sample
    </v-card-title>

    <v-divider></v-divider>

    <v-card-text>
      <v-form
        ref="form"
        v-model="valid"
        lazy-validation
      >
        <div class="text-sm-body-2">Text</div>
        <v-text-field
          outlined
          required
          dense
        ></v-text-field>

        <div class="text-sm-body-2">Password</div>
        <v-text-field
          outlined
          required
          dense
          type="password"
        ></v-text-field>

        <div class="text-sm-body-2">Select</div>
        <v-combobox
          v-model="select"
          :items="items"
          outlined
          dense
        ></v-combobox>

        <div class="text-sm-body-2">Textarea</div>
        <v-textarea
          outlined
          name="input-7-4"
        ></v-textarea>
      </v-form>
    </v-card-text>

    <v-divider></v-divider>

    <v-card-actions>
      <v-spacer></v-spacer>
      <v-btn
        outlined
        small
        color="success"
        class="mr-4"
      >
        Submit
      </v-btn>

      <v-btn
        outlined
        small
        class="mr-4"
      >
        Cancel
      </v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
  export default {
    data: () => ({
      select: 'Item 1',
      items: [
        'Item 1',
        'Item 2',
        'Item 3',
        'Item 4',
      ]
    }),
  }
</script>
