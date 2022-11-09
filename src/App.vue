<template>
  <div id="app">
    <Header></Header>
    <Content></Content>
    <!-- <header>
      <nav class="navbar navbar-expand-sm navbar-light bg-light">
        <div class="container-fluid">
          <ul class="navbar-nav">
            <li class="nav-item">
              <router-link to="/" class="nav-link">Home</router-link>
            </li>
            <li class="nav-item">
              <router-link to="/login" class="nav-link">Login</router-link>
            </li>
            <li class="nav-item">
              <router-link to="/signUp" class="nav-link">SignUP</router-link>
            </li>
          </ul>
        </div>
      </nav>
    </header> -->
    <!-- <div>
      <router-link to="/">Home|</router-link>
      <router-link to="/login">Login|</router-link>
      <router-link to="/signUp">SignUP</router-link>
    </div> -->
    <router-view />

  </div>
</template>
<script>

import Header from '@/layout/Header';
import Content from '@/layout/Content';

export default {
  name: 'App',
  components: {
    Header, Content,

  }
}
</script>


<style scoped>
/* #app {
  background-image: 'C:\project2\images';
}

.container-fluid {
  justify-content: flex-end;
} */
</style>