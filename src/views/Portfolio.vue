<template>
  <v-container grid-list-xl>
    <h2 class="pl-4">
      <span>Web</span>
      <span class="orange--text">Portfolio</span>
    </h2>
    <v-layout row justify-center align-center wrap class="mt-4 pt-2">
      <v-dialog
        v-model="project.dialog"
        max-width="800"
        v-for="project in projects"
        :key="project.title"
      >
        <template v-slot:activator="{ on }">
          <v-flex xs12 sm6 md4 lg4 xl4 v-on="on">
            <v-card hover text color="orange">
              <v-img
                :src="project.poster"
                :alt="project.title"
                height="250"
                lazy-src="img/spinner.gif"
              ></v-img>
              <v-card-title primary-title class="justify-center">{{project.title}}</v-card-title>
            </v-card>
          </v-flex>
        </template>
        <v-card v-if="project.dialog" class="d-flex flex-column align-end">
          <v-img height="70vh" :src="project.poster"></v-img>
          <v-card-text>
            <h3 class="headline my-4">
              <span>Tools</span>
            </h3>
            <div class="chip-container">
            <v-chip class="mx-1"  color="grey" text-color="white">{{project.techs.tech1}}</v-chip>
            <v-chip class="mx-1" color="grey" text-color="white">{{project.techs.tech2}}</v-chip>
            <v-chip class="mx-1" color="grey" text-color="white">{{project.techs.tech3}}</v-chip>
            <v-chip class="mx-1" color="grey" text-color="white">{{project.techs.tech4}}</v-chip>
            </div>
          </v-card-text>
          <v-card-actions class="mb-5">
            <v-btn text large dark color="orange" :href="project.git" target="_blank">
              <v-icon right>fab fa-github</v-icon>GitHub
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      dialog: false,
      projects: [
         {
          dialog: false,
          title: "Proyecto Z",
          cover: "",
          git: "https://github.com/danysainero/ProyectoZ_Angular",
          techs: {
            tech1: "Angular",
            tech2: "Azure Cognitives Services",
            tech3: "SCSS"
          }
        },
        {
          dialog: false,
          title: "My Portfolio",
          cover: "",
          git: "",
          techs: {
            tech1: "VUE",
            tech2: "Vuetify",
            tech3: "HTML",
            tech4: "SCSS"
          }
        },
       {
          dialog: false,
          title: "Blog Components",
          cover: "",
          git: "",
          techs: {
            tech1: "Stencil Js",
            tech2: "StoryBook",
            tech3: "SCSS"
          }
        },{
          dialog: false,
          title: "Blog Frontend",
          cover: "",
          git: "https://github.com/danysainero/blog-front",
          techs: {
            tech1: "Angular 9",
            tech2: "Jest",
            tech3: "Cypress",
            tech4: "SCSS",
            tech5: "PrimeNG"
          }
        },{
          dialog: false,
          title: "Blog Backend",
          cover: "",
          git: "https://github.com/danysainero/blog-back",
          techs: {
            tech1: "Node",
            tech2: "Express",
            tech3: "Jest",
            tech4: "MongoDB",
            tech5: "Mongoose",
            tech6: "JWT"
          }
        }
      ]
    };
  }
};
</script>

<style  scoped>
</style>