<template>
  <v-app id="inspire">
    <v-navigation-drawer
        v-model="drawer"
        app
        clipped
    >
      <v-list dense>
        <v-list-item
            v-for="item in items"
            :key="item.text"
            v-on:click="testfn1"
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>
              {{ item.text }}
            </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-subheader class="mt-4 grey--text text--darken-1">SUBSCRIPTIONS</v-subheader>
        <v-list>
          <v-list-item
              v-for="item in items2"
              :key="item.text"
              v-on:click="testfn2"
          >
            <v-list-item-avatar>
              <img
                  :src="`https://randomuser.me/api/portraits/men/${item.picture}.jpg`"
                  alt=""
              >
            </v-list-item-avatar>
            <v-list-item-title v-text="item.text"></v-list-item-title>
          </v-list-item>
        </v-list>
        <v-list-item
            class="mt-4"
            v-on:click="testfn3"
        >
          <v-list-item-action>
            <v-icon color="grey darken-1">fas fa-plus-circle</v-icon>
          </v-list-item-action>
          <v-list-item-title class="grey--text text--darken-1">Browse Channels</v-list-item-title>
        </v-list-item>
        <v-list-item v-on:click="testfn1">
          <v-list-item-action>
            <v-icon color="grey darken-1">fas fa-cog</v-icon>
          </v-list-item-action>
          <v-list-item-title class="grey--text text--darken-1">Manage Subscriptions</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar
        app
        clipped-left
        color="black"
        dense
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
      <v-icon class="mx-4">fab fa-youtube</v-icon>
      <v-toolbar-title class="mr-12 align-center">
        <span class="title">Youtube</span>
      </v-toolbar-title>
      <div class="flex-grow-1"></div>
      <v-row
          align="center"
          style="max-width: 650px"
      >
        <v-text-field
            :append-icon-cb="() => {}"
            placeholder="Search..."
            single-line
            append-icon="fas fa-search"
            color="white"
            hide-details
        ></v-text-field>
      </v-row>
    </v-app-bar>

    <v-content>
      <v-container class="fill-height">
        <v-row
            justify="center"
            align="center"
        >
          <v-col class="shrink">
            <v-tooltip right>
              <template v-slot:activator="{ on }">
                <v-btn
                    :href="source"
                    icon
                    large
                    target="_blank"
                    v-on="on"
                >
                  <v-icon large>fas fa-code</v-icon>
                </v-btn>
              </template>
              <span>Source</span>
            </v-tooltip>
            <v-tooltip right>
              <template v-slot:activator="{ on }">
                <v-btn
                    icon
                    large
                    href="https://codepen.io/johnjleider/pen/aezMOO"
                    target="_blank"
                    v-on="on"
                >
                  <v-icon large>fab fa-codepen</v-icon>
                </v-btn>
              </template>
              <span>Codepen</span>
            </v-tooltip>
          </v-col>
        </v-row>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
  export default {
    props: {
      source: String,
    },
    methods: {
      testfn1() {
        // eslint-disable-next-line no-console
        console.log('test 1');
      },
      testfn2() {
        // eslint-disable-next-line no-console
        console.log('test 2');
      },
      testfn3() {
        // eslint-disable-next-line no-console
        console.log('test 3');
      },
    },
    data: () => ({
      drawer: null,
      items: [
        { icon: 'fas fa-chart-line', text: 'Intro' },
        { icon: 'fas fa-address-card', text: 'Experience' },
        { icon: 'fas fa-history', text: 'Work' },
        { icon: 'fas fa-list', text: 'Social' },
        { icon: 'far fa-clock', text: 'Imprint' },
      ],
      items2: [
        { picture: 28, text: 'Joseph' },
        { picture: 38, text: 'Apple' },
        { picture: 48, text: 'Xbox Ahoy' },
        { picture: 58, text: 'Nokia' },
        { picture: 78, text: 'MKBHD' },
      ],
    }),
    created () {
      this.$vuetify.theme.dark = true
    },
  }
</script>

<!--<template>-->
<!--  <v-app>-->
<!--    <v-app-bar app>-->
<!--      <v-toolbar-title class="headline text-uppercase">-->
<!--        <span>Vuetify</span>-->
<!--        <span class="font-weight-light">MATERIAL DESIGN</span>-->
<!--      </v-toolbar-title>-->
<!--      <v-spacer></v-spacer>-->
<!--      <v-btn-->
<!--        text-->
<!--        href="https://github.com/vuetifyjs/vuetify/releases/latest"-->
<!--        target="_blank"-->
<!--      >-->
<!--        <span class="mr-2">Latest Release</span>-->
<!--      </v-btn>-->
<!--    </v-app-bar>-->

<!--    <v-content>-->
<!--      <HelloWorld/>-->
<!--    </v-content>-->
<!--  </v-app>-->
<!--</template>-->

<!--<script>-->
<!--import HelloWorld from './components/HelloWorld';-->

<!--export default {-->
<!--  name: 'App',-->
<!--  components: {-->
<!--    HelloWorld,-->
<!--  },-->
<!--  data: () => ({-->
<!--    //-->
<!--  }),-->
<!--};-->
<!--</script>-->
