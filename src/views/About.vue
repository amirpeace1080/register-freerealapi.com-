<template>
  <div class="about">
    <!-- <h4>token =  {{ this.$store.state.token }} </h4> -->
    <form>
      <label>Name: </label>
      <input type="text" v-model="name" />
      <br />
      <label>Email: </label>
      <input type="email" v-model="email" />
      <br />
      <label>Password: </label>
      <input type="text" v-model="password" />
      <br /><br />
      <button @click="aaa">Register</button>
    </form>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      name: null,
      email: null,
      password: null,
    };
  },
  methods: {
    aaa() {
      let name = this.name;
      let email = this.email;
      let password = this.password;
      axios({
        url: "https://api.freerealapi.com/auth/register",
        method: "POST",
        body: JSON.stringify({
          name: name,
          email: email,
          password: password,
        }),
      })
        .then((response) => response.json())
        .then((json) => console.log(json));
    },
  },
  mounted() {
    //  axios({
    //    url: "https://api.freerealapi.com/auth/register",
    //    method: "POST",
    //    headers: { 'Content-Type': 'application/json' },
    //   body: JSON.stringify({
    //     name: this.name,
    //     email: this.email,
    //     password: this.password,
    //   })
    // })
    // .then((response) => response.json())
    // .then((json) => console.log(json))
  },
};
</script>

<style></style>
