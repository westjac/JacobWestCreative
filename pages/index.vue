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
          color="white">Photo</v-btn>
        <v-btn
          href="http://www.youtube.com/c/JacobWest"
          target="_blank"
          class="ma-2"
          outlined
          large
          color="white">Video</v-btn>
        <v-btn
          to="/code"
          class="ma-2"
          outlined
          large
          color="white">Code</v-btn>
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
