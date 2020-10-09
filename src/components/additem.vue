<template>
  <div>
    <v-form ref="form" v-model="valid" lazy-validation>
      <v-text-field v-model="Name" label="Name" required></v-text-field>
      <v-text-field
        v-model="Review"
        style="1"
        label="Text Review"
        required
      ></v-text-field>
      <v-text-field
        v-model="Point"
        type="number"
        style="1"
        label="Point"
        required
      ></v-text-field>
      <v-checkbox
        v-model="status"
        value="Too Good"
        label="Too Good"
        required
      ></v-checkbox>
      <v-checkbox
        v-model="status"
        value="Too Bad"
        label="Too Bad"
        required
      ></v-checkbox>
      <v-btn :disabled="!valid" color="success" class="mr-4" @click="validate">
        Validate
      </v-btn>
      <v-btn color="error" class="mr-4" @click="reset"> Reset Form </v-btn>
    </v-form>
  </div>
</template>

<script>
export default {
  data: () => ({
    valid: true,
    Name: "",
    Review: "",
    status: "",
    Point: "",
    select: null,
    checkbox: false,
  }),
  methods: {
    validate() {
      if (this.Name) {
        let payload = {
          Review: this.Review,
          Point: this.Point,
          status: this.status,
          Name: this.Name
        };
        this.$store.dispatch("setItem", payload);
      }
    },
    reset() {
      this.$refs.form.reset();
    },
    page() {
      this.$store.state.page = 2;
    },
  },
};
</script>

<style>
</style>