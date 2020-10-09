<template>
  <div class="text-center">
    <v-row no-gutters>
      <v-col md="2"><v-card class="pa-2 info white--text" outlined> id</v-card></v-col>
      <v-col md="2"><v-card class="pa-2 info white--text" outlined> Name</v-card></v-col>
      <v-col md="4"><v-card class="pa-2 info white--text" outlined> Text Review</v-card></v-col>
      <v-col md="2"><v-card class="pa-2 info white--text" outlined> Point</v-card></v-col>
      <v-col md="2"> <v-card class="pa-2 info white--text" outlined> status</v-card></v-col>
    </v-row>
    <v-row v-for="(items, index) in $store.getters.items" :key="index"  no-gutters>
      <v-col md="2"><v-card class="pa-2" outlined> {{ index + 1 }}</v-card></v-col>
      <v-col md="2"><v-card class="pa-2" outlined> {{ items.Name }}</v-card></v-col>
      <v-col md="4"><v-card class="pa-2" outlined> {{ items.Review }}</v-card></v-col>
      <v-col md="2"><v-card class="pa-2" outlined> {{ items.Point }}</v-card></v-col>
      <v-col md="2"><v-card class="pa-2" outlined> {{ items.status }}</v-card></v-col>
      <td></td>
    </v-row>
  </div>
</template>

<script>
export default {
  methods: {
    page() {
      this.$store.state.page = 1;
    },
  },
};
</script>

<style>
</style>