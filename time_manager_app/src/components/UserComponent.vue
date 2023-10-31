<template>
  <h1 >Ajouter un utilisateur</h1>
  <form v-on:submit.prevent="postUser">
    <input type="text" v-model="username" placeholder="Nom d'utilisateur">
    <input type="text" v-model="email" placeholder="Email">
    <button>Enregistrer</button>
  </form>
</template>

<script>
import axios from "axios";

export default {
  name: "CreateUserConponent",

  data() {
    return {
      id: "10",
      username: "",
      email: ""
    };
  },

  methods: {
    postUser() {
      const userData = {
        username: this.username,
        email: this.email
      }
      axios.post(`http://localhost:4000/api/users`, userData).then(response => {
        console.log(response);
      })
    }
  }

  // methods: {
  //   postUser() {
  //     axios.get(`http://localhost:4000/api/users`).then(response => {
  //       console.log(response);
  //     })
  //   }
  // }
}

</script>
