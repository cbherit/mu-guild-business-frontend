<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link> |
      <router-link to="/orders">Orders</router-link> |
      <router-link to="/my-orders">MyOrders</router-link> |
      <router-link to="/order-history">MyOrderHistory</router-link> |
      <router-link to="/login">Login</router-link> |
      <button @click="logout">Logout</button>
    </div>
    <router-view/>
  </div>
</template>

<script>
import { mapActions} from 'vuex'

export default {
   methods: {
     ...mapActions(['readToken', 'logout'])
   },
   created(){
     this.readToken()
   }
}
</script>

<style>
*, *::before, *::after {
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
