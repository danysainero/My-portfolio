<template>
  <v-layout row justify-center align-center wrap class="mt-12 pt-2">
    <v-flex xs12 sm12 md5 lg6 xl6 class="mt-4 pt-4">
      <h2>Formación</h2>
      <v-card-text class="py-0">
        <v-timeline align-top dense>
          <v-timeline-item color="orange" small>
            <v-layout pt-3>
              <v-flex xs4>
                <div class="caption font-weight-bold orange--text">03/2020 -</div>
                <div class="caption font-weight-bold orange--text">07/2020</div>
              </v-flex>
              <v-flex class="pl-2">
                <strong>Fullstack Web Development</strong>
                <div class="caption mb-2">Kairos DS</div>
              </v-flex>
            </v-layout>
          </v-timeline-item>
          <v-timeline-item color="orange" small>
            <v-layout pt-3>
              <v-flex xs4>
                <div class="caption font-weight-bold orange--text">01/2020 -</div>
                <div class="caption font-weight-bold orange--text">03/2020</div>
              </v-flex>
              <v-flex class="pl-2">
                <strong>Curso Vue + Vuex</strong>
                <div class="caption mb-2">Fictizia</div>
              </v-flex>
            </v-layout>
          </v-timeline-item>
          <v-timeline-item color="orange" small>
            <v-layout pt-3>
              <v-flex xs4>
                <div class="caption font-weight-bold orange--text">03/2019 -</div>
                <div class="caption font-weight-bold orange--text">08/2019</div>
              </v-flex>
              <v-flex class="pl-2">
                <strong>Bootcamp Fullstack MEAN</strong>
                <div class="caption mb-2">Boream</div>
              </v-flex>
            </v-layout>
          </v-timeline-item>

          <v-timeline-item color="orange" small>
            <v-layout pt-3>
              <v-flex xs4>
                <div class="caption font-weight-bold orange--text">09/2017 -</div>
                <div class="caption font-weight-bold orange--text">06/2019</div>
              </v-flex>
              <v-flex class="pl-2">
                <strong>FP Microinformática y redes</strong>
                <div class="caption mb-2">IE Cantabria</div>
              </v-flex>
            </v-layout>
          </v-timeline-item>
        </v-timeline>
      </v-card-text>
    </v-flex>
    <v-flex xs12 sm12 md4 lg6 xl6 class="mt-4 pt-2">
      <h2>Experiencia</h2>
      <v-card-text class="py-0">
        <v-timeline align-top dense>
          <v-timeline-item color="orange" small>
            <v-layout pt-3>
              <v-flex xs4>
                <div class="caption font-weight-bold orange--text">03/2020 -</div>
                <div class="caption font-weight-bold orange--text">07/2020</div>
              </v-flex>
              <v-flex class="pl-2">
                <strong>Junior Fullstack Developer</strong>
                <div class="caption mb-2">Kairos DS</div>
              </v-flex>
            </v-layout>
          </v-timeline-item>

          <v-timeline-item color="orange" small>
            <v-layout pt-3>
              <v-flex xs4>
                <div class="caption font-weight-bold orange--text">08/2019 -</div>
                <div class="caption font-weight-bold orange--text">02/2020</div>
              </v-flex>
              <v-flex class="pl-2">
                <strong>Junior Frontend Developer</strong>
                <div class="caption mb-2">Schrodinger Lab</div>
              </v-flex>
            </v-layout>
          </v-timeline-item>

          <v-timeline-item color="orange" small>
            <v-layout pt-3>
              <v-flex xs4>
                <div class="caption font-weight-bold orange--text">AUG 2014 -</div>
                <div class="caption font-weight-bold orange--text">APR 2016</div>
              </v-flex>
              <v-flex class="pl-2">
                <strong>Técnico soporte E-commerce</strong>
                <div class="caption mb-2">Correos S.A</div>
              </v-flex>
            </v-layout>
          </v-timeline-item>
          <v-timeline-item color="orange" small>
            <v-layout pt-3>
              <v-flex xs4>
                <div class="caption font-weight-bold orange--text">09/2011 -</div>
                <div class="caption font-weight-bold orange--text">06/2017</div>
              </v-flex>
              <v-flex class="pl-2">
                <strong>Team Leader Quality</strong>
                <div class="caption mb-2">Lyreco (Alemania)</div>
              </v-flex>
            </v-layout>
          </v-timeline-item>
        </v-timeline>
      </v-card-text>
    </v-flex>
    <v-layout row justify-center align-center wrap class="mt-4 pt-3">
      <v-flex xs12 sm12 md3 lg3 xl12 class="mx-9 pt-9">
        <h2>
          <span>Frontend</span>
          <span class="orange--text">Skills</span>
        </h2>
        <strong>Angular</strong>
        <v-progress-linear v-model="buffer1" :buffer-value="bufferValue" color="orange" height="16"></v-progress-linear>
        <strong>Vue</strong>
        <v-progress-linear v-model="buffer2" :buffer-value="bufferValue" color="orange" height="16"></v-progress-linear>
        <strong>JavaScript</strong>
        <v-progress-linear v-model="buffer3" :buffer-value="bufferValue" color="orange" height="16"></v-progress-linear>
        <strong>Stencil</strong>
        <v-progress-linear v-model="buffer4" :buffer-value="bufferValue" color="orange" height="16"></v-progress-linear>
        <strong>Git / Git flow</strong>
        <v-progress-linear v-model="buffer5" :buffer-value="bufferValue" color="orange" height="16"></v-progress-linear>
      </v-flex>

      <v-flex xs12 sm12 md3 lg3 xl12 class="mx-9 pt-9">
        <h2>
          <span>Backend</span>
          <span class="orange--text">Skills</span>
        </h2>
        <strong>Node Js</strong>
        <v-progress-linear v-model="buffer6" :buffer-value="bufferValue" color="orange" height="16"></v-progress-linear>
        <strong>Express</strong>
        <v-progress-linear v-model="buffer7" :buffer-value="bufferValue" color="orange" height="16"></v-progress-linear>
        <strong>Koa</strong>
        <v-progress-linear v-model="buffer8" :buffer-value="bufferValue" color="orange" height="16"></v-progress-linear>
        <strong>MongoDB</strong>
        <v-progress-linear v-model="buffer9" :buffer-value="bufferValue" color="orange" height="16"></v-progress-linear>
        <strong>Docker</strong>
        <v-progress-linear
          v-model="buffer10"
          :buffer-value="bufferValue"
          color="orange"
          height="16"
        ></v-progress-linear>
      </v-flex>

      <v-flex xs12 sm12 md3 lg3 xl12 class="mx-9 pt-9">
        <h2>
          <span>Other</span>
          <span class="orange--text">Skills</span>
        </h2>
        <strong>Agile / Scrum</strong>
        <v-progress-linear
          v-model="buffer11"
          :buffer-value="bufferValue"
          color="orange"
          height="16"
        ></v-progress-linear>
        <strong>Figma</strong>
        <v-progress-linear
          v-model="buffer12"
          :buffer-value="bufferValue"
          color="orange"
          height="16"
        ></v-progress-linear>
        <strong>Adobe XD</strong>
        <v-progress-linear
          v-model="buffer13"
          :buffer-value="bufferValue"
          color="orange"
          height="16"
        ></v-progress-linear>
        <strong>Jira / Trello</strong>
        <v-progress-linear
          v-model="buffer14"
          :buffer-value="bufferValue"
          color="orange"
          height="16"
        ></v-progress-linear>
        <strong>Zeplin</strong>
        <v-progress-linear
          v-model="buffer15"
          :buffer-value="bufferValue"
          color="orange"
          height="16"
        ></v-progress-linear>
      </v-flex>

      <div class="my-16 pt-2">
        <v-btn
          href="https://drive.google.com/file/d/1Wzmzm2-hic7LuLIgzdmqMJioCXL8-XqR/view?usp=sharing"
          target="_blank"
          dark
          large
          class="btn-download"
        >
          Download Resume
          <v-icon right dark>fas fa-file-download</v-icon>
        </v-btn>
      </div>
    </v-layout>
  </v-layout>
</template>

<script>
export default {
  data() {
    return {
      value: 0,
      buffer1: 0,
      buffer2: 0,
      buffer3: 0,
      buffer4: 0,
      buffer5: 0,
      buffer6: 0,
      buffer7: 0,
      buffer8: 0,
      buffer9: 0,
      buffer10: 0,
      buffer11: 0,
      buffer12: 0,
      buffer13: 0,
      buffer14: 0,
      buffer15: 0,
      bufferValue: 100,
      interval: 0
    };
  },
  mounted() {
    this.startBuffer();
  },

  beforeDestroy() {
    clearInterval(this.interval);
  },

  methods: {
    startBuffer() {
      this.interval = setInterval(() => {
        this.buffer1 = 70;
        this.buffer2 = 65;
        this.buffer3 = 80;
        this.buffer4 = 70;
        this.buffer5 = 80;
        this.buffer6 = 70;
        this.buffer7 = 75;
        this.buffer8 = 65;
        this.buffer9 = 60;
        this.buffer10 = 60;
        this.buffer11 = 80;
        this.buffer12 = 90;
        this.buffer13 = 90;
        this.buffer14 = 80;
        this.buffer15 = 90;
      }, 800);
    }
  }
};
</script>
<style lang="scss">
.btn-download {
  animation: myfirst 3s infinite;
  -moz-animation: myfirst 3s infinite;
  -webkit-animation: myfirst 3s infinite;
}

@-moz-keyframes myfirst {
  0% {
    background: rgb(43, 43, 43);
  }
  50% {
    background: rgb(143, 142, 142);
  }
  100% {
    background: rgb(43, 43, 43);
  }
}

@keyframes myfirst {
  0% {
    background: rgb(43, 43, 43);
  }
  50% {
    background: rgb(143, 142, 142);
  }
  100% {
    background: rgb(43, 43, 43);
  }
}
</style>

