<script setup>
  import Header from './components/HeaderComponent.vue';
  import About from './components/AboutMeComponent.vue';
  import Home from './components/HomeComponent.vue';
  import Login from './components/LoginComponent.vue';
  import SideNav from './components/SideNavComponent.vue';
  import { ref, watch} from 'vue';

  console.log("1.1 Components initialized"); 

  const log = ref(false);
  const calour = ref("blue");
  const hStat = ref(false);

  function logStatuss(isLoged) {
    log.value = isLoged; 
  }

  function logoutStatus(isLogout) {
    log.value = isLogout;
  }

  watch(log, (newCalour) => {
    calour.value = newCalour ? "lightgreen": "blue";
    console.log("3.1 Header updated for signed-in state");
  })

  watch(log, () => {
    if (log.value == true) {
      console.log("3.2 SideNav rendered");
      console.log("5.1 Home rendered");
      console.log("3.3 Default view rendered");
    }
  })

  function homeStatuss(home) {
    hStat.value = home;
  }
</script>

<template>
    <div id="Nav">
      <Header :background="calour" :statuss="log" @LogoutStatus="logoutStatus"/>
      <div id="sideNav" v-if="log">
        <SideNav/>
      </div>
    </div>
    <div>
      <div id="login" v-if="!log">
        <Login @loginStatus="logStatuss"/>
      </div>
      <div v-if="log || hStat">
        <Home @homeStatus="homeStatuss"/>
      </div>
    </div>
</template>

<style scoped>

  #Nav {
    display: block;
    padding: 1rem;
    height: 70px;
    position: relative;
    top: -25px;
    margin-left: -25px;
    margin-right: -25px;
  }

  #sideNav {
    display: inline-block;
    position: relative;
    left: 85%;
    top: -60px;
  }

  #login {
    display: flex;
    justify-content: center;
    margin-top: 5rem; 
  }
</style>
