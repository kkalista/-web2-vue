<template>
  <div id="app">
  <h1>Witaj w systemie do zapisów na zajecia</h1>
    <div v-if="isAuthenticated">
        <h2> Zalogowany jako {{email}}</h2>      
      <button @click="logOut()">Wyloguj</button>
    </div>

    <div v-else>
      <p>Zaloguj sie mailem <input type="email" v-model="email">
      <button @click="logIn()">Wchodzę</button>
    </p>
    </div>
    
    </div>

</template>

<script>
import "milligram";

export default {
  name: "app",
  data() {
    return {
      email: "",
      isAuthenticated: false
    };
  },
  methods: {
    logIn() {
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
