<template>
  <v-row justify="center">
    <v-col cols="6">
      <v-card>
        <v-card-title> login </v-card-title>
        <v-card-text>
          <v-text-field
            :prepend-icon="'mdi-email-outline'"
            name="input-10-1"
            label="email"
            v-model="email"
          ></v-text-field>
          <v-text-field
            :prepend-icon="'mdi-lock-outline'"
            name="input-10-1"
            label="password"
            counter
            v-model="password"
          ></v-text-field>
        </v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn @click="logout" text>logOut</v-btn>
          <v-btn @click="login" text>login</v-btn>
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
</template>
<script>
export default {
  data: () => ({
    email: "",
    password: "",
  }),

  methods: {
    login() {
      this.$auth.loginWith("laravelJWT", {
        data: {
          email: this.email,
          password: this.password,
        },
      });
    },
    logout() {
      console.log("logout");
      this.$auth.logout()
    },
  },
};
</script>
