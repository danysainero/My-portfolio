<template>
  <v-container grid-list-xl class="mt-12">
    <v-layout row justify-center align-center wrap class="m-4 pt-12">
      <v-dialog
        v-model="project.dialog"
        max-width="800"
        v-for="project in projects"
        :key="project.title"
      >
        <template v-slot:activator="{ on }">
          <v-flex xs12 sm6 md4 lg4 xl4 v-on="on">
            <v-card hover text color="#FB8705">
              <v-img
                :src="project.cover"
                :alt="project.title"
                hover
                height="250"
                max-width="100%"
                lazy-src="img/spinner.gif"
              ></v-img>
              <v-card-title primary-title >{{project.title}}</v-card-title>
            </v-card>
          </v-flex>
        </template>
        <v-card v-if="project.dialog" class="d-flex flex-column align-end">
          <v-img  max-width="95%" max-height="60vh" :src="project.cover" class=" mx-auto my-4"></v-img>
          <v-card-text>
            <h3 class="headline my-4 text-center">
              <span class="text-sm-center text-md-center ">Tools</span>
            </h3>
            <div class="d-flex flex-wrap justify-center">
             <v-chip label v-for="(tech, index) in project.techs" :key="index" class="mx-1 my-1"   color="grey" text-color="white">{{tech}}</v-chip>
         </div>
          </v-card-text>
          <v-card-actions>
            <v-btn text large hover color="white" :href="project.git" target="_blank" class="orange mx-2">
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
          cover: "img/proyectoz.jpg",
          git: "https://github.com/danysainero/ProyectoZ_Angular",
          techs: {
            tech1: "Angular",
            tech2: "Azure",
            tech3: "Face Recognition",
            tech4: "SCSS",
          }
        },
        {
          dialog: false,
          title: "My Portfolio",
          cover: "img/myportfolio.jpg",
          git: "https://github.com/danysainero/My-portfolio",
          techs: {
            tech1: "VUE",
            tech2: "Vuetify",
            tech3: "HTML",
            tech4: "SCSS"
          }
        },
        {
          dialog: false,
          title: "Face Recognition",
          cover: "img/faces.jpg",
          git: "https://github.com/danysainero/Face-recognition",
          techs: {
            tech1: "JavaScript",
            tech2: "Azure",
            tech3: "HTML",
            tech4: "Cognitive Services",
            tech5: "Jquery"
          }
        },
        {
          dialog: false,
          title: "Clon Netflix",
          cover: "img/Netflix-Clon.jpg",
          git: "https://github.com/danysainero/Netflix-Angular",
          techs: {
            tech1: "Angular",
            tech2: "TypeScript",
            tech3: "HTML",
            tech4: "Video API"
          }
        },
        {
          dialog: false,
          title: "Spotify Player",
          cover: "img/spotify-clon.jpg",
          git: "https://github.com/danysainero/Spotify-Clon-Player",
          techs: {
            tech1: "JavaScript",
            tech2: "SCSS",
            tech3: "HTML",
            tech4: "Audio API",
            tech5: "Sketch"
          }
        },
       {
          dialog: false,
          title: "Blog Components",
          cover: "img/blog-components.jpg",
          git: "https://github.com/danysainero/blog-stenciljs-components",
          techs: {
            tech1: "StencilJs",
            tech2: "StoryBook",
            tech3: "SCSS"
          }
        },{
          dialog: false,
          title: "Blog Frontend",
          cover: "img/blog.jpg",
          git: "https://github.com/danysainero/blog-front",
          techs: {
            tech1: "Angular 9",
            tech2: "Jest",
            tech3: "Cypress",
            tech4: "Docker",
            tech5: "PrimeNG",
            tech6: "StencilJs"
          }
        },{
          dialog: false,
          title: "Blog Backend",
          cover: "img/blog-back.jpg",
          git: "https://github.com/danysainero/blog-back",
          techs: {
            tech1: "Node",
            tech2: "Express",
            tech3: "Jest",
            tech4: "MongoDB",
            tech5: "Mongoose",
            tech6: "Docker"
          }
        },
        {
          dialog: false,
          title: "AI-tanks Hackaton test",
          cover: "img/tanks.jpg",
          git: "https://github.com/danysainero/AI-tanks-Javascript",
          techs: {
            tech1: "JavaScript",
            tech2: "PHASER",
            tech3: "CSS",
            tech4: "HTML"
          }
        },
        {
          dialog: false,
          title: "Contacts Book",
          cover: "img/contacts.jpg",
          git: "https://github.com/danysainero/agenda-contactos_reto_individual",
          techs: {
            tech1: "JavaScript",
            tech2: "HTML",
            tech3: "SCSS",
            tech4: "MIXINS"
          }
        }
      ]
    };
  }
};
</script>

<style  scoped>

</style>