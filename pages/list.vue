<template>
  <v-card
    class="mx-auto"
    max-width="1200s"
  >
    <v-toolbar
      color="pink"
      dark
    >
      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-toolbar-title>Inbox</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-checkbox-marked-circle</v-icon>
      </v-btn>
    </v-toolbar>
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
    <v-list two-line>
      <v-list-item-group
        v-model="selected"
        active-class="pink--text"
        multiple
      >
        <template v-for="(item, index) in filteredItems">
          <v-list-item :key="item.title">
            <template v-slot:default="{ active }">
              <v-list-item-content>
                <v-list-item-title v-text="item.title"></v-list-item-title>

                <v-list-item-subtitle
                  class="text--primary"
                  v-text="item.headline"
                ></v-list-item-subtitle>

                <v-list-item-subtitle v-text="item.subtitle"></v-list-item-subtitle>
              </v-list-item-content>

              <v-list-item-action>
                <v-list-item-action-text v-text="item.action"></v-list-item-action-text>

                <v-icon
                  v-if="!active"
                  color="grey lighten-1"
                >
                  mdi-star-outline
                </v-icon>

                <v-icon
                  v-else
                  color="yellow darken-3"
                >
                  mdi-star
                </v-icon>
              </v-list-item-action>
            </template>
          </v-list-item>

          <v-divider
            v-if="index < items.length - 1"
            :key="index"
          ></v-divider>
        </template>
      </v-list-item-group>
    </v-list>
  </v-card>
</template>
<script>
export default {
  data () {
    return {
      selected: [],
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
      items: [
        {
          action: '15 min',
          headline: 'Brunch this weekend?',
          subtitle: "I'll be in your neighborhood doing errands this weekend. Do you want to hang out?",
          title: 'Ali Connors',
          status : 'a',
          type : 'b'
        },
        {
          action: '2 hr',
          headline: 'Summer BBQ',
          subtitle: "Wish I could come, but I'm out of town this weekend.",
          title: 'me, Scrott, Jennifer',
          status : 'a',
          type : 'c'
        },
        {
          action: '6 hr',
          headline: 'Oui oui',
          subtitle: 'Do you have Paris recommendations? Have you ever been?',
          title: 'Sandra Adams',
          status : 'b',
          type : 'a'
        },
        {
          action: '12 hr',
          headline: 'Birthday gift',
          subtitle: 'Have any ideas about what we should get Heidi for her birthday?',
          title: 'Trevor Hansen',
          status : 'c',
          type : 'd'
        },
        {
          action: '18hr',
          headline: 'Recipe to try',
          subtitle: 'We should eat this: Grate, Squash, Corn, and tomatillo Tacos.',
          title: 'Britta Holt',
          status : 'd',
          type : 'a'
        }
      ],
    }
  },
  computed: {
    filteredItems() {
      return this.items.filter(item => {
        if(!this.search) return this.items;
        return (item.title.toLowerCase().includes(this.search.toLowerCase()) ||
          item.action.toLowerCase().includes(this.search.toLowerCase())   ||
          item.headline.toLowerCase().includes(this.search.toLowerCase()) ||
          item.subtitle.toLowerCase().includes(this.search.toLowerCase()));
      });
    }
  },
  methods: {
    clearSearch () {
      this.search="";
    },
    statusFilter(value) {
      return this.items.filter(item => {
        if(!value) return this.items;
        return (item.status.includes(value));
      });
    }
  }
}
</script>
