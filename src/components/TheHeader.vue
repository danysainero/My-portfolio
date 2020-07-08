<template>
<div>
  <v-app-bar fixed elevate-on-scroll
      >
      <v-app-bar-nav-icon icon class="hidden-md-and-up orange--text" @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title>
        <span class="font-weight-light">Dany </span>
        <span class="orange--text"> Sainero</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn @click="changeTheme" depressed small icon class="hidden-md-and-up">
        <v-icon v-if="goDark==true" >fas fa-sun</v-icon>
        <v-icon v-else>fas fa-moon</v-icon>
      </v-btn>
      <v-toolbar-items class="hidden-sm-and-down">
        <v-btn text to="/" active-class="orange--text headline" class="mx-2">Home</v-btn>
        <v-btn text to="/resume" active-class="orange--text headline" class="mx-2">Resume</v-btn>
        <v-btn text to="/portfolio" active-class="orange--text headline" class="mx-2">Portfolio</v-btn>
        <v-btn text to="/contact" active-class="orange--text headline" class="mx-2">Contact</v-btn>
        <v-btn @click="changeTheme" depressed small icon>
          <v-icon v-if="goDark==true">fas fa-sun</v-icon>
          <v-icon v-else>fas fa-moon</v-icon>
        </v-btn>
      </v-toolbar-items>
    </v-app-bar>

     <v-navigation-drawer v-model="drawer" absolute temporary app width="150">
      <v-list class="pt-4">

        <v-list-item active-class="orange--text" to="/">
          <v-list-item-content>
            <v-list-item-title>HOME</v-list-item-title>
          </v-list-item-content>
        </v-list-item>

        <v-list-item active-class="orange--text" to="/resume">
          <v-list-item-content>
            <v-list-item-title>RESUME</v-list-item-title>
          </v-list-item-content>
        </v-list-item>

        <v-list-item active-class="orange--text" to="/portfolio">
          <v-list-item-content>
            <v-list-item-title>PORTFOLIO</v-list-item-title>
          </v-list-item-content>
        </v-list-item>

        <v-list-item active-class="orange--text" to="/contact">
          <v-list-item-content>
            <v-list-item-title>CONTACT</v-list-item-title>
          </v-list-item-content>
        </v-list-item>

      </v-list>
    </v-navigation-drawer>
    
</div>
</template>
<script>
export default {
  data() {
    return {
      drawer: null,
      collapseOnScroll: true,
    };
  },
  props: {
    goDark: {
      type: Boolean
    }
  },
  methods: {
    changeTheme() {
      this.$emit("changeTheme", this.goDark);
    }
  }
};
</script>
  <style lang="scss">
.text-green .v-label {
  font-size: 0.875rem;
  font-weight: 500;
}
</style>