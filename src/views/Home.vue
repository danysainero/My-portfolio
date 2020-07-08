<template>
  <v-layout column justify-center align-center class="mt-12 pt-2">
    <VueCompareImage
      class="hidden-md-and-down"
      hover
      :style="{ minWidth: '1300px' }"
      :sliderLineWidth="sliderLine"
      :handleSize="hSize"
      :leftImage="leftImage"
      :rightImage="rightImage"
      :sliderPositionPercentage="sliderPosition"
    />
    <VueCompareImage
     id="img-container"
      class="hidden-lg-and-up my-12"
      hover
      :style="{ maxWidth: '400px'}"
      :sliderLineWidth="sliderLine"
      :handleSize="hSize"
          :leftImage="leftImage"
      :rightImage="rightImage"
      :sliderPositionPercentage="sliderPosition"
    />
    <v-flex>
      <v-card flat  max-width="650">
        <v-card-title>
          <h3 class="heading">
            <span class="orange--text font-weight-bold heading1">Hola!</span>
          </h3>
        </v-card-title>
        <v-card-text class="home-text ">
          <p>
            Mi nombre es Daniel Sainero, soy desarrollador
            <span
              class="grey--text font-weight-bold"
            >FRONTEND</span> con conocimientos de
            <span class="grey--text font-weight-bold">BACKEND</span> y
            <span class="grey--text font-weight-bold">DISEÑO</span>. He trabajado con
            <span
              class="grey--text font-weight-bold"
            >ANGULAR</span>
            y
            <span class="grey--text font-weight-bold">VUE</span>. Viví durante 8 años en Alemania, pero decidí volver para dedicarme a lo que de verdad me apasiona, 
            <span class="orange--text font-weight-bold text-uppercase"> la programación.</span>
            
          </p>
        </v-card-text>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
import VueCompareImage from "vue-compare-image";

export default {
  components: {
    VueCompareImage
  },
  data() {
    return {
      text1: ["Front-End Developer", "Back-End Developer"],
      leftImage: "/front1.jpg",
      rightImage: "/back1.png",
      sliderLine: 0,
      hSize: 0,
      sliderPosition: 0.5
    };
  }
};
</script>
<style lang="scss">
.home-text{
  font-size: 1.4rem;
  line-height: 1.2;
  text-align: justify;
}

</style>

