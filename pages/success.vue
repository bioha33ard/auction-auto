<template>
  <v-container class="mt-15 mb-15 d-flex justify-center">
    <v-alert type="success" max-width="50rem">
      <h2>{{ $t('success_title') }}</h2>
      <p>{{ $t('success_text') }}</p>
    </v-alert>
  </v-container>
</template>

<script>
export default {
  name: "success"
}
</script>

<style scoped>

</style>
