<template>
    <h1>Users List</h1>
    <ul class="item" v-for="item in list" :key="item.id">
        <li>{{ item.id }}</li>
        <li>{{ item.email }}</li>
        <li>{{ item.first_name }}</li>
        <li><img :src="item.avatar"/></li>
    </ul>
  </template>
  
  <script>
  import axios from 'axios';
  export default {
      name: "API",
      data() {
          return {
              list: [],
          };
      },
      async mounted() {
          let result = await axios.get("https://reqres.in/api/users?page=1");
          console.log("api data", result.data.data);
          this.list = result.data.data;
      },
  }
  </script>
  
  <style>

  .item{
    display: flex;
    justify-content: center;
    height: auto;   
  }

  .item img {
    width : 50px;
  }

  .item li {
    display: inline-block;
    width: 200px;
    border: 1px solid;
    text-align: center;
    padding: 5px;
  }
  
  </style>
  