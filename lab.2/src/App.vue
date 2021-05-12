<template>
  <div class="bg-light">
    <Navbar :signedIn="signedIn" @pls-login="plsLogIn = true" @log-out="logOut" />
    <div class="container" v-if="plsLogIn">
      <Signin class="bg-secondary" @sign-in="signIn" />
    </div>
    <Footer />
  </div>
</template>

<script>
import Navbar from "./components/Navbar";
import Footer from "./components/Footer";
import Signin from "./components/Signin";

export default {
  name: "App",
  components: {
    Navbar,
    Signin,
    Footer,
  },
  data() {
    return {
      signedIn: null, // Variable for the signed in user
      plsLogIn: false,
      users: [
        { id: "1", name: "Ida", pass: "1234" },
        { id: "2", name: "Mina", pass: "1234" },
        { id: "3", name: "Tina", pass: "1234" },
        { id: "4", name: "Sara", pass: "1234" },
      ],
    };
  },
  methods: {
    signIn(user) {
      if(user.name !== '' && user.pass !== '') {
        this.users.push(user);
        this.signedIn = user;
        this.plsLogIn = false; // Remove form when user is signed in.
      } else if(user.name == '' && user.pass == '')
        alert('Please enter your username and password!')
      else if(user.pass == '')
        alert('Please enter your password!')
      else
        alert('Please enter your username!')
    },
    logOut() {
      this.signedIn = null; // Removes the signed in user.
    },
  },
};
</script>

<style>
.btn-success {
  background-color: #41b883;
  border-color: #41b883;
}
.btn-success:hover {
  background-color: #1a3a2c;
  border-color: #1a3a2c;
}
</style>

