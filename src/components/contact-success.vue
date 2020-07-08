
 <template>
  <v-row justify="center">
    <v-dialog
      v-model="dialog"
      max-width="290"
    >
      <v-card>
        <v-card-title class="headline">Mensaje recibido!!!</v-card-title>

        <v-card-text>
          Contestaré a tu mensaje lo antes posible, gracias!!!.
        </v-card-text>

        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn
            color="orange darken-1"
            text
            @click="dialog = false"
          >
            Ok!
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-row>
</template>

<script>
  export default {
    data () {
      return {
        dialog: true,
      }
    },
  }
</script>