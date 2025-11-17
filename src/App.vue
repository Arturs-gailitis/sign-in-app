<script setup>
  import Header from './components/HeaderComponent.vue';
  import About from './components/AboutMeComponent.vue';
  import Home from './components/HomeComponent.vue';
  import Login from './components/LoginComponent.vue';
  import SideNav from './components/SideNavComponent.vue';
  import { ref, watch} from 'vue';

  console.log("1.1 Components initialized"); 

  const log = ref(false);
  const calour = ref("#979797ff");
  const hStat = ref(false);
  const aStat = ref(false);

  function logStatuss(isLoged) {
    log.value = isLoged; 
  }

  function logoutStatus(isLogout) {
    log.value = isLogout;
  }

  watch(log, (newCalour) => {
    calour.value = newCalour ? "#FFECBDff": "#979797ff";
    console.log("3.1 Header updated for signed-in state");
  })

  watch(log, () => {
    if (log.value == true) {
      console.log("3.2 SideNav rendered");
      console.log("5.1 Home rendered");
      console.log("3.3 Default view: Home");
    }
  })

  function homeStatuss(home) {
    hStat.value = home;
  }

  function aboutStatuss(about) {
    aStat.value = about;
  }

  watch(aStat, () => {
    if (aStat.value == true) {
      hStat.value = false;
    }
  })

  watch(hStat, () => {
    if (hStat.value == true) {
      aStat.value = false;
    }
  })
</script>

<template>
    <div id="Nav">
      <Header :background="calour" :statuss="log" @LogoutStatus="logoutStatus"/>
      <div id="sideNav" v-if="log">
        <SideNav @homeStatus="homeStatuss" @aboutStatus="aboutStatuss"/>
      </div>
    </div>
    <div>
      <div id="login" v-if="!log">
        <Login @loginStatus="logStatuss"/>
      </div>
      <div v-if="(log && hStat) || (log && !aStat) ">
        <Home/>
      </div>
      <div v-if="aStat && log">
        <About/>
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
    top: 40%;
    margin-top: -27px;
    background-color: #C6FAF6ff;
    height: 613px;
    width: 200px;
  }

  #login {
    display: flex;
    justify-content: center;
    margin-top: 5rem; 
  }
</style>
