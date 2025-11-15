<script setup>
  import Header from './components/HeaderComponent.vue';
  import About from './components/AboutMeComponent.vue';
  import Home from './components/HomeComponent.vue';
  import Login from './components/LoginComponent.vue';
  import SideNav from './components/SideNavComponent.vue';

  console.log("1.1 Components initialized");
</script>

<template>
    <div id="navBar">
      <div id="header">
        <Header />
      </div>
      <div id="sideNav">
        <SideNav />
      </div>
    </div>
</template>

<style scoped>
  #navBar {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 1rem;
    background-color: blue;
  }

  #header {
    display: flex;
  }

  #sideNav {
    display: flex;
  }
</style>
