<template>
  <div>
      <h2>Witaj {{ authenticatedUsername }}</h2>
      <a @click="logMeOut()">Wyloguj</a>
  </div>
</template>

<script>
export default {
    name: "UserPage",
    methods: {
        enter() {
            this.$emit('logout');
        }
    },
}
</script>

<style>

</style>