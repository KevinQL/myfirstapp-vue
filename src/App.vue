<template>
  <div id="app">
    <h1>APP TITLE</h1>
    <!-- <HelloWorld /> -->
    <!-- <Test 
      msg="My props is a msg" /> -->
    <!-- <User /> -->


    <div>
      <h1>COMPONENT ROUTER</h1>
      <ul>
        <li>
          <router-link to="/">User</router-link>
        </li>
        <li>
          <router-link to="/test">Test</router-link>
        </li>
      </ul>
      <hr>
      <div>
        <router-view></router-view>
      </div>

    </div>

  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import Test from "./components/Test";
import User from "./components/User";

export default {
  name: 'App',
  components: {
    HelloWorld,
    Test,
    User,
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
