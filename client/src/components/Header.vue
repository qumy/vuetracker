<template>
  <v-toolbar fixed class="cyan">    
    <v-toolbar-title class="mr-4" @click="navigateTo({name: 'root'})">
      <v-toolbar-side-icon></v-toolbar-side-icon>
    </v-toolbar-title>
    <v-spacer></v-spacer>
    <v-toolbar-items class="hidden-sm-and-down">
      <v-btn
        flat
        @click="navigateTo({ name: 'songs'})">
        Songs
      </v-btn>
      <v-btn 
        flat 
        @click="navigateTo({ name: 'login' })">
        Enter
      </v-btn>
      <v-btn 
        v-if="$store.state.isUserLoggedIn"
        flat 
        @click="navigateTo({ name: 'logout' })">
        Logout
      </v-btn>
      <v-btn 
        v-if="!$store.state.isUserLoggedIn"
        flat 
        :to="{ name: 'register' }">
        Register
      </v-btn>
    </v-toolbar-items>
  </v-toolbar>
</template>

<script>
export default {
  methods: {
    navigateTo(route) {
      this.$router.push(route);
    },
    logout() {
      this.$store.dispatch("setToken", null);
      this.$store.dispatch("setUser", null);
      this.$router.push({
        name: "root"
      });
    }
  }
};
</script>
<style scoped>
.home {
  cursor: pointer;
}
.home.hover {
  color: #e9e;
}
</style>
