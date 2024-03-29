<template>
    <div>
      <h1>Sign Up</h1>
      <form @submit.prevent="submitForm">
        <div class="form-group">
          <label for="email">Email:</label>
          <input type="email" class="form-control" id="email" v-model="email" required>
        </div>
        <div class="form-group">
          <label for="firstName">First Name:</label>
          <input type="text" class="form-control" id="firstName" v-model="first_name" required>
        </div>
        <div class="form-group">
          <label for="lastName">Last Name:</label>
          <input type="text" class="form-control" id="lastName" v-model="last_name" required>
        </div>
        <div class="form-group">
          <label for="avatarUrl">Avatar URL:</label>
          <input type="text" class="form-control" id="avatarUrl" v-model="avatar" required>
        </div>
        <button type="submit" class="btn btn-primary">Submit</button>
      </form>
    </div>
  </template>
  
  <script>
  import axios from 'axios';
  export default {
    name: "SignUpForm",
    data() {
      return {
        email: '',
        first_name: '',
        last_name: '',
        avatar: ''
      }
    },
    methods: {
      submitForm() {
        this.addUser();
      },
      addUser() {
        axios.post("https://reqres.in/api/users", {
          email: this.email,
          first_name: this.first_name,
          last_name: this.last_name,
          avatar: this.avatar
        }).then(response => {
          console.log("User added:", response.data);
          this.email = '';
          this.first_name = '';
          this.last_name = '';
          this.avatar = '';
        }).catch(error => {
          console.error("Error adding user:", error);
        });
      }
    }
  }
  </script>
  
  <style>

  </style>
  