<template>
  <div class="my-app">
    <h1>WItaj w sysytemie do zapisów na zajęcia!</h1>

    <div v-if="loggedIn">
      Zalogowany!
      <div>
        <button @click="backToMainPage()">Wyloguj</button>
      </div>
    </div>
    <div v-else>
      <input type="email" v-model="email" placeholder="Type your e-mail">
      <button @click="checkIfProperAddress()">Zaloguj</button>
    </div>

    <div v-if="!email.includes('@')"> E-mail powinine zawierać "@"!</div>

<!--    <div v-else-if="email.length < 10">Ale masz krótki adres ({{email.length}})!</div>-->
<!--    <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>-->
<!--    <div v-else>Twój adres e-mail jest stanowczo za długi ({{email.length}})!</div>-->
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: '',
      password: '',
      loggedIn: false
    };
  },

  methods: {
    alertMyEmail() {
      alert(this.email);
    },

    checkIfProperAddress() {
      if (this.email.includes('@')) {
        this.loggedIn = true;
      }
    },

    backToMainPage() {
      this.loggedIn = false;
      this.email = '';
    }
  }
}
</script>

<style>
.my-app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
}
</style>
