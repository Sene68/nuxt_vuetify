<template>
  <v-card
    max-width="1200"
    class="mx-auto"
  >
    <v-system-bar
      color="pink darken-2"
      dark
    >
      <v-spacer></v-spacer>

      <v-icon>mdi-window-minimize</v-icon>

      <v-icon>mdi-window-maximize</v-icon>

      <v-icon>mdi-close</v-icon>
    </v-system-bar>

    <v-app-bar
      dark
      color="pink"
    >
      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-toolbar-title>My Music</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>
    </v-app-bar>
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
    <v-container>
      <v-row dense>
<!--        <v-col cols="12">-->
<!--          <v-card-->
<!--            color="#385F73"-->
<!--            dark-->
<!--          >-->
<!--            <v-card-title class="headline">-->
<!--              Unlimited music now-->
<!--            </v-card-title>-->

<!--            <v-card-subtitle>Listen to your favorite artists and albums whenever and wherever, online and offline.</v-card-subtitle>-->

<!--            <v-card-actions>-->
<!--              <v-btn text>-->
<!--                Listen Now-->
<!--              </v-btn>-->
<!--            </v-card-actions>-->
<!--          </v-card>-->
<!--        </v-col>-->

<!--        <v-col-->
<!--          v-for="(item, i) in filteredItems"-->
<!--          :key="i"-->
<!--          cols="12"-->
<!--        >-->
        <template v-for="item in filteredItems">
          <v-col cols="12" :key="item.title">
            <v-card
              :color="item.color"
              dark
            >
              <div class="d-flex flex-no-wrap justify-space-between">
                <div>
                  <v-card-title
                    class="headline"
                    v-text="item.title"
                  ></v-card-title>

                  <v-card-subtitle v-text="item.artist"></v-card-subtitle>

                  <v-divider/>

                  <v-card-actions>
                    <v-btn
                      v-if="item.artist === 'Ellie Goulding'"
                      class="ml-2 mt-3"
                      fab
                      icon
                      height="40px"
                      right
                      width="40px"
                    >
                      <v-icon>mdi-play</v-icon>
                    </v-btn>

                    <v-btn
                      v-else
                      class="ml-2 mt-5"
                      outlined
                      rounded
                      small
                    >
                      START RADIO
                    </v-btn>
                  </v-card-actions>
                </div>

                <v-avatar
                  class="ma-3"
                  size="125"
                  tile
                >
                  <v-img :src="item.src"></v-img>
                </v-avatar>
              </div>
            </v-card>
          </v-col>
        </template>
      </v-row>
    </v-container>
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
            color: '#303a3b',
            src: 'https://cdn.vuetifyjs.com/images/cards/foster.jpg',
            title: 'Supermodel',
            artist: 'Foster the People',
            status : 'aa',
            type : 'c'
          },
          {
            color: '#303a3b',
            src: 'https://cdn.vuetifyjs.com/images/cards/halcyon.png',
            title: 'Halfwerfwecyon Days',
            artist: 'Ellie Gou123123lding',
            status : 'aa',
            type : 'b'
          },
          {
            color: '#303a3b',
            src: 'https://cdn.vuetifyjs.com/images/cards/halcyon.png',
            title: 'Halcyon Dawefwefys',
            artist: 'Ellie Goulding',
            status : 'bb',
            type : 'a'
          },
          {
            color: '#303a3b',
            src: 'https://cdn.vuetifyjs.com/images/cards/halcyon.png',
            title: 'Halcyfqfqfqon Days',
            artist: 'Ellie Goulding',
            status : 'cc',
            type : 'd'
          },
          {
            color: '#303a3b',
            src: 'https://cdn.vuetifyjs.com/images/cards/halcyon.png',
            title: 'Halcgsdfgdfbyon Days',
            artist: 'Ellie Goulding',
            status : 'dd',
            type : 'a'
          }
        ],
      }
    },
    computed: {
      filteredItems() {
        console.log(this.search)
        console.log(this.selectStatus)
        console.log(this.selectType)
        return this.items.filter(item => {
          if(!this.search && !this.selectStatus && !this.selectType) return this.items;
          return (item.title.toLowerCase().includes(this.search.toLowerCase()) && item.status.includes(this.selectStatus) && item.type.includes(this.selectType));
        });
      }
    },
    methods: {
      statusFilter(value) {
        return this.items.filter(item => {
          if(!value) return this.items;
          return (item.status.includes(value));
        });
      }
    }
}
</script>
