<template>
  <v-app>
    <v-main>
      <v-container align-center>
        <TheHeader :goDark="goDark" @changeTheme="updateTheme($event)" />

        <transition
          name="router-animation"
          mode="out-in"
          enter-active-class="animated fadeIn fast"
          leave-active-class="animated fadeOut faster"
        >
          <router-view></router-view>
        </transition>
      </v-container>
    </v-main>
    <!-- <TheFooter/> -->
  </v-app>
</template>

<script>
import TheHeader from "./components/TheHeader";
/* import TheFooter from "./components/TheFooter"; */

export default {
  name: "App",
  components: {
    TheHeader
    /*   TheFooter */
  },
  data() {
    return { goDark: false };
  },
  methods: {
    updateTheme(updatedTheme) {
      this.goDark = !updatedTheme;
      this.$vuetify.theme.dark = !updatedTheme;
    }
  }
};
</script>
<style>
@import "https://cdnjs.cloudflare.com/ajax/libs/animate.css/3.7.0/animate.min.css";

*::selection{
  background: #FF9800;
  color: rgb(0, 0, 0);
}
</style>