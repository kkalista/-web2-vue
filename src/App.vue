<template>
  <div id="app">
  <h1>Witaj w systemie do zapisow na zajecia</h1>

<login-form
    v-if="!isAuthenticated"
     @login="logIn($event)">
    </login-form>
    <div v-else>
       <label> Zalogowany jako {{email}}</label>      
      <button @click="logOut()">Wyloguj</button>
    </div>
</div>

</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";
//import MeetingPage from "./meetings/MeetingPage";

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
