<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <logo />
      <div class="text-center">
        <v-btn
          to="/photo"
          class="ma-2"
          outlined
          large
          color="white">
          Photo
        </v-btn>
        <v-btn
          to="/web"
          class="ma-2"
          outlined
          large
          color="white">
          Websites
        </v-btn>
        <v-btn
          href="https://www.youtube.com/channel/UCiLhIQvzkE5qempPPvArq1w"
          target = "_blank"
          class="ma-2"
          outlined
          large
          color="white">
          Video
        </v-btn>
      </div>
    </v-col>
  </v-row>
</template>

<script>
import Logo from '~/components/logo.vue'

export default {
  components: {
    Logo
  }
}
</script>
