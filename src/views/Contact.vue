<template>
  <v-container grid-list-xl class="mt-12">
    <v-layout row justify-center align-center wrap class="mt-8">
      <v-flex xs12 sm12 md6 lg6 xl6>
        <h2 class="pb-8">
          <span>Contacto</span>
        </h2>
        <div class="py-4 font-weight-bold">
          <v-icon large color="orange" left class="mr-2">fas fa-map-marker-alt</v-icon>
          <span>Madrid, España</span>
        </div>
        <div class="py-4 font-weight-bold">
          <v-icon large color="orange" left>fa fa-at</v-icon>
          <span>danysainero@gmail.com</span>
        </div>
        <div class="py-4 font-weight-bold">
          <v-icon large color="orange" left>fas fa-phone</v-icon>
          <span>+34 603 77 03 34</span>
        </div>
        <div class="py-4 font-weight-bold">
          <v-icon large color="orange" left>fa fa-user-circle</v-icon>
          <a class="secondary--text" href="http://www.linkedin.com/in/dany-sain" target="_blank">
            <span class="text-lowercase">www.linkedin.com/in/dany-sain</span>
          </a>
        </div>
      </v-flex>

      <v-flex xs12 sm12 md6 lg6 xl6>
        <h2 class="mt-12">
          <span>Hablamos?</span>
        </h2>

        <form
          name="ask-question"
          method="post"
          v-on:submit.prevent="handleSubmit"
          action="/success/"
          data-netlify="true"
          data-netlify-honeypot="bot-field"
        >
          <input type="hidden" name="form-name" value="ask-question" />
          <v-text-field
            name="name"
            color="orange"
            background-color="transparent"
            v-model="formData.name"
            label="Name"
            required
          ></v-text-field>
          <v-text-field
            type="email"
            color="orange"
            background-color="transparent"
            name="email"
            v-model="formData.email"
            label="E-mail"
            required
          ></v-text-field>
          <v-textarea
            color="orange"
            background-color="transparent"
            :counter="200"
            v-model="formData.message"
            label="Textarea"
            name="message"
          ></v-textarea>
          <p hidden>
            <label>
              Don’t fill this out:
              <input name="bot-field" />
            </label>
          </p>
          <v-btn @click="submit" type="submit" color="orange" class="white--text">SEND MESSAGE</v-btn>
          <v-btn @click="clear">clear</v-btn>
        </form>
      </v-flex>
    </v-layout>
    <router-view></router-view>
  </v-container>
</template>

<script>
import { validationMixin } from "vuelidate";
import {
  required,
  maxLength,
  email,
  minLength
} from "vuelidate/lib/validators";
export default {
  mixins: [validationMixin],
  validations: {
    name: { required, minLength: minLength(3), maxLength: maxLength(20) },
    email: { required, email },
    body: { required, minLength: minLength(10) }
  },
  data() {
    return {
      formData: {
        name: "",
        email: "",
        message: ""
      }
    };
  },
  methods: {
    clear() {
      this.formData.name = "";
      this.formData.email = "";
      this.formData.message = "";
    },
    encode(data) {
      return Object.keys(data)
        .map(
          key => encodeURIComponent(key) + "=" + encodeURIComponent(data[key])
        )
        .join("&");
    },
    handleSubmit(e) {
      fetch("/", {
        method: "POST",
        headers: { "Content-Type": "application/x-www-form-urlencoded" },
        body: this.encode({
          "form-name": e.target.getAttribute("name"),
          ...this.formData
        })
      })
        .then(() => {
          this.formData.name = "";
          this.formData.email = "";
          this.formData.message = "";
          this.$router.push("contact/success");
        })
        .catch(error => alert(error));
    }
  }
};
</script>

<style lang="scss" scoped>
</style>
