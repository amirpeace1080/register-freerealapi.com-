<template>
  <div class="home">
    <h1>{{ this.$store.state.token }}</h1>

    <label>Email: </label>
    <input type="text" v-model="email" />
    <br />
    <label>Password: </label>
    <input type="text" v-model="password" />
    <br /><br />
    <button @click="login">login</button>
  </div>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      email: null,
      password: null,
    };
  },
  methods: {
    login() {
      let email = this.email;
      let password = this.password;
      this.$store.dispatch("login", { email, password });
    },
  },
};
</script>
