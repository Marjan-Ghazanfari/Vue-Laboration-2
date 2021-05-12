<template>
  <form class="z-depth-10 shadow-lg rounded-3 mb-5" @submit.prevent="btnFunction">
    <div class="py-4 row my-5 text-center text-white">
      <h3>Login Form</h3>
    </div>
    <div class="row mb-3 justify-content-center">
      <div class="col-4">
        <input type="text" id="userName" class="form-control" placeholder="User Name..." v-model="userName" />
      </div>
    </div>
    <div class="row mb-5 justify-content-center">
      <div class="col-4">
        <input type="password" class="form-control" placeholder="Password..." v-model="pass" />
      </div>
    </div>
    <div class="row">
      <div class="mb-3 d-flex justify-content-center">
        <button type="submit" class="btn btn-success">Log in</button>
      </div>
    </div>
  </form>
</template>

<script>
export default {
  data() {
    return {
      userName: "",
      pass: "",
    };
  },
  methods: {
    btnFunction() {
      this.$emit("sign-in", {
        id: Date.now(),
        name: this.userName,
        pass: this.pass,
      });
    },
  },
};
</script>

<style>
</style>