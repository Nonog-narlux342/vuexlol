<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />

        <v-img
          alt="Vuetify Name"
          class="shrink mt-1 hidden-sm-and-down"
          contain
          min-width="100"
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
          width="100"
        />
      </div>

      <v-spacer></v-spacer>
    </v-app-bar>

    <v-main>
      <HelloWorld/>
      <v-container>
        <div>
          <additem />
        </div>
        <br><hr><br>
        <div>
          <datatable />
        </div>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld';
import additem from "./components/additem";
import datatable from "./components/datatable"

export default {
  name: 'App',

  components: {
    HelloWorld,
    additem,
    datatable
  },
  data() {
    return {
      page : 1,
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          title: "Search",
          to: "/",
        },
        {
          title: "About Me",
          to: "/datatable",
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
    };
  },
  
};
</script>
