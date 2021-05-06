<template>
    <div>
        <nav class="navbar navbar-light bg-secondary shadow mb-5">
            <div class="container">
                <a class="navbar-brand" href="#">
                    <img src="../assets/images/logo.png" class="logotype">
                </a>
                <form class="d-flex" v-if="signedIn" @submit.prevent="logOut">
                    <p class="mx-3 mt-2 userName">Welcome {{ users[users.length-1].name }}!</p>
                    <button class="btn btn-success" type="submit">Log out</button>
                </form>
                <form class="d-flex" v-else @submit.prevent="logIn">
                    <button class="btn btn-success" type="submit">Please Log in</button>
                </form>
            </div>
        </nav>
        <div class="container" v-if="plsLogIn">
            <Signin class="bg-secondary" :signedIn="checkSignIn" :plsLogIn="plsLogIn" :users="users" />
        </div>
    </div>
</template>

<script>
import Signin from './Signin'

export default {
    props: ['users'],
    components: {
        Signin
    },
    data() {
        return {
            plsLogIn: false,
            signedIn: true
        }
    },
    computed: {
        checkSignIn() {
            return this.signedIn
        }
    },
    methods: {
        logIn() {
            this.plsLogIn = true
        },
        logOut() {
            this.signedIn = false
        }
    }
}
</script>

<style scoped>
.logotype {
    height: 50px;
    width: auto;
}
.userName {
    font-weight: bold;
    font:italic;
    /* font-size: 2rem; */
}
</style>