<template>
  <div class="my-app">
    <h1>Witaj w systemie do zapisów na zajęcia</h1>
<!--    <h1>Twój e-mail to {{ email }}</h1>-->

      <div v-if=!logInActive>Zaloguj się e-mailem <input type="email" v-model="email"> <button @click="logIn()">Wyświetl mój e-mail w alercie</button></div>
      <div v-else><h2>Witaj {{email}}!</h2>
          <button @click="logOut()">Wyloguj</button>
      </div>

<!--    <div v-if="!email.includes('@')">Twój email nie ma małpy!</div>-->
<!--    <div v-else-if="email.length < 10">Ale masz krótki adres! {{email.length}} znaków to za mało</div>-->
<!--    <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>-->
<!--    <div v-else>Twój adres e-mail jest stanowczo za długi. Ma {{ email.length }} znaków</div>-->

  </div>

</template>

<script>
export default {
  data() {
    return {
      email: 'moj@email.com',
      password: '',
      logInActive: false
    };
  },
  methods: {
    logIn() {
      this.logInActive = true;
    },
    logOut() {
        this.logInActive = false;
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
