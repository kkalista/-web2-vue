<template>
   <div>     
    <div v-if="isAuthenticated">
        <h2> Witaj {{email}} !</h2>      
      <button @click="logout()">Wyloguj</button>
      <meeting-page></meeting-page>
    </div>

   <div v-else>
       <h4>Zaloguj sie mailem <input type="email" v-model="email"></h4>
        <div v-if="email.length < 5"><p>Ale masz krótki adres!</p></div>
        <div v-else-if="email.length < 15"><p>Twój adres e-mail jest w sam raz.</p></div>
        <div v-else><p>Twój adres e-mail jest stanowczo za długi.</p></div>  
     <button @click="enter()">Wchodzę</button>   
    </div>
       
   </div>
</template>

<script>
import MeetingPage from "./meetings/MeetingPage";
export default {
    components: { MeetingPage },
  name: "loginForm",
  data() {
    return {
      email: "", 
      isAuthenticated: false
    };
  },
  methods: {
    enter() {
      this.$emit("login", this.email);
      this.isAuthenticated = true;
    },
    logout() {
      this.$emit('logout');
      this.isAuthenticated = false;
    }
  }
};
</script>