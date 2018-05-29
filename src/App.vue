<template>
  <div id="app">
  <h1>Witaj w systemie do zapisow na zajecia</h1>
    <login-form></login-form>
</div>

</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";

export default {
  name: "app",
  components: { LoginForm },
  data() {
    return {
      email: "",
      isAuthenticated: false
    };
  },
  methods: {
    logIn(username) {
      this.authenticatedUsername = username;
      this.isAuthenticated = true;
    },
    logOut() {
      this.isAuthenticated = false;
    }
  }
};
</script>

<style lang="scss">
</style>
