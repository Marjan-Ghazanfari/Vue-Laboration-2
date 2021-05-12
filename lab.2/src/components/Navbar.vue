<template>
  <div>
    <nav class="navbar navbar-light bg-secondary shadow mb-5">
      <div class="container">
        <a class="navbar-brand" href="#">
          <img src="../assets/images/logo.png" class="logotype" />
        </a>
        <form class="d-flex" v-if="signedIn" @submit.prevent="logOut">
          <p class="mx-3 mt-2 userName">Welcome {{ signedIn.name }}!</p>
          <button class="btn btn-success" type="submit">Log out</button>
        </form>
        <form class="d-flex" v-else @submit.prevent="logIn">
          <button class="btn btn-success" type="submit">Please Log in</button>
        </form>
      </div>
    </nav>
  </div>
</template>

<script>

export default {
  props: ['signedIn'],
  computed: {
    checkSignIn() {
      return this.signedIn;
    },
  },
  methods: {
    logIn() {
      this.$emit("pls-login");
    },
    logOut() {
      this.$emit("log-out");
    },
  },
};
</script>

<style scoped>
.logotype {
  height: 50px;
  width: auto;
}
.userName {
  font-weight: bold;
  font: italic;
}
</style>