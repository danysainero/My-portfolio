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
          netlify
          netlify-honeypot="bot-field"
          name="ask-question"
          method="post"
          data-netlify="true"
          data-netlify-honeypot="bot-field"
        >
          <v-text-field
            name="name"
            color="orange"
            background-color="transparent"
            v-model="name"
            :error-messages="nameErrors"
            label="Name"
            required
            @blur="$v.name.$touch()"
          ></v-text-field>
          <v-text-field
            type="email"
            color="orange"
            background-color="transparent"
            name="email"
            v-model="email"
            :error-messages="emailErrors"
            label="E-mail"
            required
            @blur="$v.email.$touch()"
          ></v-text-field>
          <v-textarea
            color="orange"
            background-color="transparent"
            :counter="200"
            :error-messages="bodyErrors"
            v-model="body"
            label="Textarea"
            name="body"
            @blur="$v.body.$touch()"
          ></v-textarea>
          <p class="hidden">
            <label>
              Don’t fill this out if you're human:
              <input name="bot-field" />
            </label>
          </p>
          <v-btn
            @click="submit"
            type="submit"
            color="orange"
            class="white--text"
            :disabled=" (body.length<=10)"
          >SEND MESSAGE</v-btn>
          <v-btn @click="clear">clear</v-btn>
        </form>
      </v-flex>
    </v-layout>
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
      name: "",
      email: "",
      body: ""
    };
  },
  methods: {
    submit() {
      this.$v.$touch();
    },
    clear() {
      this.$v.$reset();
      this.name = "";
      this.email = "";
      this.body = "";
    }
  },
  computed: {
    nameErrors() {
      const errors = [];
      if (!this.$v.name.$dirty) return errors;
      !this.$v.name.minLength &&
        errors.push("Text must be at least 3 characters long");
      !this.$v.name.maxLength &&
        errors.push("Name must be at most 3 characters long");
      !this.$v.name.required && errors.push("Name is required.");
      return errors;
    },
    emailErrors() {
      const errors = [];
      if (!this.$v.email.$dirty) return errors;
      !this.$v.email.email && errors.push("Must be valid e-mail");
      !this.$v.email.required && errors.push("E-mail is required");
      return errors;
    },
    bodyErrors() {
      const errors = [];
      if (!this.$v.body.$dirty) return errors;
      !this.$v.body.minLength &&
        errors.push("Text must be at least 10 characters long");
      !this.$v.body.required && errors.push("Text is required");
      return errors;
    }
  }
};
</script>

<style lang="scss" scoped>
</style>
