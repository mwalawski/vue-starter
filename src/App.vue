<template>
    <div>
        <h1>Witaj w systemie do zapisów na zajęcia</h1>

        <div v-if="authenticatedUsername">
            <UserPage @logout="logMeOut()"></UserPage>
        </div>

        <div v-else>
            <LoginForm @login="(username) => logMeIn(username)" button-label="Wejdź"></LoginForm>
         </div>

    </div>
</template>

<script>
    import "milligram";
    import LoginForm from "./LoginForm";
    import UserPage from "@/UserPage.vue";

    export default {
        components: {UserPage, LoginForm},
        data() {
            return {
                authenticatedUsername: '',
            }
        },
        methods: {
            logMeIn(username) {
                this.authenticatedUsername = username;
            },
            logMeOut() {
                this.authenticatedUsername = '';
            }
        }
    }
</script>
