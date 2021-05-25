<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <div class="text-center">
        <photoGallery />
      </div>
    </v-col>
  </v-row>
</template>

<script>
import photoGallery from '~/components/photoGallery.vue'
export default {
  components: {
    photoGallery
  }
}
</script>
