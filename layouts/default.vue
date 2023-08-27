<template>
  <v-app>
      <section id="header">
        <v-app-bar elevation="0" color="transparent">
          <v-img :src="require('@/assets/image/logo.png')" width="11rem" class="ml-5"></v-img>
          <v-list-item class="d-inline-flex justify-end">
                <v-btn text color="white"
                       v-for="locale in availableLocales"
                       :key="locale.code"
                       :to="switchLocalePath(locale.code)">
                  <h1>{{ locale.name }}</h1>
                </v-btn>
          </v-list-item>
        </v-app-bar>
        <v-container>
            <div class="header-banner-text">
              <h1>{{$t('header_text')}}</h1>
            </div>
        </v-container>
      </section>
      <v-main>
        <nuxt></nuxt>
      </v-main>
    <v-footer
      dark
      padless
      color="#af0101"
      class="d-flex justify-center"
    >
      <v-card
        flat
        tile
        class="lighten-1 white--text text-center pa-5"
        color="#af0101"
        width="50rem"
      >
        <v-card-text class="white--text pt-0">
         <b>{{$t('footer_text')}}</b>
        </v-card-text>

        <v-divider></v-divider>

        <v-card-text class="white--text">
          {{ new Date().getFullYear() }} — <strong>Auction Auto Inter Car Export</strong>
        </v-card-text>
      </v-card>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  computed: {
    availableLocales () {
      return this.$i18n.locales.filter(i => i.code !== this.$i18n.locale)
    }
  }
}

</script>
<style scoped>
  #header {
    background:url('@/assets/image/header-car.png') no-repeat center center;
    background-size: cover;
    color: white;
    padding: 10px;
    margin-bottom: 2.5rem;
    height: 100%;
  }
  .header-banner-text {
    height: 29rem;
    padding: 5rem;
    width: 100%;
  }
  .header-banner-text h1
  {
    font-size:5.5vh;
    font-weight: 700;
    margin: 0 auto;
    color: #ffffff;
    width: 50%;
    position: absolute;
    left: 5rem;
  }
</style>
