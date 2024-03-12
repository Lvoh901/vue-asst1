<template>
  <div class="nav">
    <RouterLink class="nav-item" to="/">Home</RouterLink>
    <RouterLink class="nav-item" to="/login">Login</RouterLink>
    <RouterLink class="nav-item" to="/signup">SignUp</RouterLink>
    <RouterLink class="nav-item" to="/reset">Password Reset</RouterLink>
  </div>

  <router-view></router-view>
</template>

<script></script>

<style scoped>
.nav {
  display: flex;
  justify-content: center;
  gap: 2em;
  padding: 15px;
  font-family: Georgia, 'Times New Roman', Times, serif;
  -webkit-box-shadow: 0px 10px 7px -9px rgba(0, 0, 0, 0.75);
  -moz-box-shadow: 0px 10px 7px -9px rgba(0, 0, 0, 0.75);
  box-shadow: 0px 10px 7px -9px rgba(0, 0, 0, 0.75);
}

.nav-item {
  text-decoration: none;
  color: #000;
}

.nav-item:hover {
  color: orangered;
}
</style>
