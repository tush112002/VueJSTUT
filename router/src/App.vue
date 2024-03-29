<template>
<div class="router-links">
    <router-link to="/">Home</router-link>
    <router-link to="/login">Login</router-link>
    <router-link to="/profile">Profile</router-link>
    <router-link to="/profile/1">User 1 Profile</router-link>
    <router-link to="/profile/2">User 2 Profile</router-link>
</div>
<router-view></router-view>
</template>

<script>

export default {
    name: 'App'
}
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
.router-links {
    display: flex;
    gap: 10px;
    justify-content: center;
}

</style>
