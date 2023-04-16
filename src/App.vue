<template>
  <div class="my-app">
    <h1>Witaj w sysytemie do zapisów na zajęcia!</h1>

    <div v-if="authenticatedUsername.length > 0">
      Zalogowany jako {{authenticatedUsername}}!
      <div>
        <button @click="logOut()">Wyloguj</button>
      </div>
    </div>
    <div v-else>

      //Dadać tutaj teg ochld component
      <LoginForm @login="(username) => logMeIn(username)"></LoginForm>

<!--      <input type="email" v-model="email" placeholder="Type your e-mail">-->
<!--      <button @click="checkIfProperAddress()">Zaloguj</button>-->
<!--    </div>-->

<!--    <div v-else-if="email.length < 10">Ale masz krótki adres ({{email.length}})!</div>-->
<!--    <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>-->
<!--    <div v-else>Twój adres e-mail jest stanowczo za długi ({{email.length}})!</div>-->
    </div>
  </div>
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";

export default {
  components: {LoginForm},

  data() {
    return {
      authenticatedUsername: '',
      password: '',
      // loggedIn: false
    };
  },

  methods: {
    logMeIn(username) {
      this.authenticatedUsername = username;
    },

    logOut() {
      this.authenticatedUsername = '';
    }

    // alertMyEmail() {
    //   alert(this.email);
    // },

    // logMeIn(username) {
    //   this.email = username;
    //   this.loggedIn = true;
    // },

    // logMeOut() {
    //   this.loggedIn = false;
    //   this.email = '';
    // }

    // checkIfProperAddress() {
    //   if (this.email.includes('@')) {
    //     this.loggedIn = true;
    //   }
    // },

    // backToMainPage() {
    //   this.loggedIn = false;
    //   this.email = '';
    // }
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
