<template>
  <v-app>
    <v-parallax
    absolute
        src="https://mentaldisaster.eu/modules/revsliderprestashop/uploads/dopelove_1.png"
    >
    <v-main>
      <router-view/>
    </v-main>
    </v-parallax>
  </v-app>
</template>

<script>

export default {
  name: 'App',

  data: () => ({
    //
  }),
};
</script>

