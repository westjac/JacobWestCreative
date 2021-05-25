<template>
  <v-row>
    <v-col
      v-for="n in 4"
      :key="n"
      class="d-flex child-flex"
      cols="4"
    >
      <v-img
        :src="`/photoGallery/${n}.png`"
        aspect-ratio="1"
        class="grey lighten-2"
      >
        <template v-slot:placeholder>
          <v-row
            class="fill-height ma-0"
            align="center"
            justify="center"
          >
            <v-progress-circular
              indeterminate
              color="grey lighten-5"
            ></v-progress-circular>
          </v-row>
        </template>
      </v-img>
    </v-col>
  </v-row>
</template>
