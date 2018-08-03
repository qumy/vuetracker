<template>
  <v-toolbar fixed class="cyan">
    <v-toolbar-side-icon></v-toolbar-side-icon>
    <v-toolbar-title class="mr-4" @click="navigateTo({name: 'root'})"><span class="home">Главная</span></v-toolbar-title>
    <v-spacer></v-spacer>
    <v-toolbar-items class="hidden-sm-and-down">
      <v-btn 
        flat 
        @click="navigateTo({ name: 'login' })">
        Войти
      </v-btn>
      <v-btn 
        flat 
        @click="navigateTo({ name: 'logout' })">
        Выйти
      </v-btn>
      <v-btn 
        flat 
        :to="{ name: 'register' }">
        Регистрация
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
