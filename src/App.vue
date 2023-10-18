<script>
import HeaderComponent from "@/components/HeaderComponent.vue";
import NavigationComponent from "@/components/NavigationComponent.vue";
import HomeComponent from "@/components/HomeComponent.vue";
import AboutMeComponent from "@/components/AboutMeComponent.vue";

export default {
  components: {
    HeaderComponent,
    NavigationComponent,
    HomeComponent,
    AboutMeComponent,
  },
  data() {
    return {
      currentTab: "home",
      isLoggedIn: false,
    };
  },
  methods: {
    changeTab(tab) {
      this.currentTab = tab;
    },
    toggleLoginStatus() {
      (this.isLoggedIn) ? this.currentTab = 'home' : null; //if logged out, it defaults to homepage when logging in next time
      this.isLoggedIn = !this.isLoggedIn;
    },
  },
};
</script>
<template>
  <div id="app">
    <header class="header">
      <HeaderComponent @toggleLoginStatus="toggleLoginStatus"/>
    </header>
    <div v-show=isLoggedIn class="grid-container" >
        <NavigationComponent  :currentTab="currentTab" @changeTab="changeTab" />
      <div>
        <HomeComponent  v-if="currentTab === 'home'" />
        <AboutMeComponent  v-if="currentTab === 'aboutMe'" />
      </div>
    </div>
  </div>
</template>

<style>
#app {
  width: 100%;
  height: 100vh;
  background-color: rgb(22, 17, 29);
}

.grid-container {
  display: grid;
  grid-template-columns: 400px auto;
}
.grid-container > div{
  margin-top: 10px;
  text-align: left;
}

</style>
