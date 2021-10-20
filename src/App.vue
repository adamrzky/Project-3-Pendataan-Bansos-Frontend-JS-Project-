<style>
  @import 'https://fonts.googleapis.com/css?family=Lato:100,300,400,500,700,900';
  @import './assets/css/styles.css';
</style>

<template>
  <v-app>
    <navigation />
    <Dialog />

    <v-main class="grey lighten-2">
      <home />
      <contact />
        <v-slide-x-transition leave-absolute>
          <router-view />
        </v-slide-x-transition>
    </v-main>
    <v-scale-transition>
  
    </v-scale-transition>
    <foote />
  </v-app>
</template>
<style scoped>
.v-main {
  background-image: url("~@/assets/img/bgMain.png");
  background-attachment: fixed;
  background-position: center;
  background-size: cover;
}
</style>
<script>
import navigation from "./components/Navigation";
// import contact from "./components/Contact";
import home from "./components/HomeSection";  
import foote from "./components/Footer"
export default {
  name: "App",
  components: {
    navigation,
    home,
    // contact,
    Dialog : () => import(/* webpackChunkName: "about" */ './components/Dialog.vue'),
    foote
  },
  
  
};
</script>
