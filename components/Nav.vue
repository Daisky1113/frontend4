<template>
  <v-app-bar fixed app>
    <v-spacer />
    <template v-if="this.$auth.loggedIn">
      <v-btn text @click="logout">ろぐあうと</v-btn>
    </template>
  </v-app-bar>
</template>
<script>
export default {
  methods: {
    logout() {
      this.$auth.logout();
    },
  },
};
</script>
