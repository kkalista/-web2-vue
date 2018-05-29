<template>
   <div>
       <label>Zaloguj sie emailem</label> 
       <input type="email" v-model="email">
       <button @click="enter()">Wchodze</button>
   </div>
</template>

<script>
export default {
 data() {
     return {
         email: ''
     }
 },
 methods: {
     enter() {
         this.$emit('login', email);
     }
 }
}
</script>