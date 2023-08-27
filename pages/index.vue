<template>
  <v-container>
    <h1 class="text-center">{{$t('steps_of_work')}}</h1>
    <v-card flat class="pa-5">
      <v-row>
        <v-col cols="12" class="d-inline-flex justify-center">
          <v-card :img="require('@/assets/image/car-1.png')" rounded  width="100%" height="30rem">
            <div class="card-wrapper ">
              <h1>1.</h1>
              <div class="card-wrapper-text">
                <h2>{{ $t('request') }}</h2>
                <p>{{ $t('request_text') }}</p>
                <v-btn class="mb-5" href="/order" color="primary" x-large>{{ $t('send_request') }}</v-btn>

              </div>
            </div>
          </v-card>
        </v-col>
      </v-row>
      <v-row>
        <v-col cols="6" class="d-inline-flex justify-center">
          <v-card :img="require('@/assets/image/car-2.png')" rounded  width="100%" height="30rem">
            <div class="card-wrapper ">
              <h1>2.</h1>
              <div class="card-wrapper-text">
                <h2>{{ $t('formation') }}</h2>
                <p>{{ $t('formation_text')}}</p>
              </div>
            </div>
          </v-card>
        </v-col>
        <v-col cols="6" class="d-inline-flex justify-center">
          <v-card :img="require('@/assets/image/car-3.png')" rounded  width="100%" height="30rem">
            <div class="card-wrapper ">
              <h1>3.</h1>
              <div class="card-wrapper-text">
                <h2>{{ $t('search_selection_purchase') }}</h2>
                <p>{{ $t('search_selection_purchase_text')}}</p>
              </div>
            </div>
          </v-card>
        </v-col>
      </v-row>
      <v-row>
        <v-col cols="7" class="d-inline-flex justify-center">
          <v-card :img="require('@/assets/image/car-4.jpg')" rounded  width="100%" height="30rem">
            <div class="card-wrapper ">
              <h1>4.</h1>
              <div class="card-wrapper-text">
                <h2>{{ $t('delivery_and_clearance') }}</h2>
                <p>{{ $t('delivery_and_clearance_text') }}</p>
              </div>
            </div>
          </v-card>
        </v-col>
        <v-col cols="5" class="d-inline-flex justify-center">
          <v-card :img="require('@/assets/image/car-5.jpg')" rounded  width="100%" height="30rem">
            <div class="card-wrapper ">
              <h1>5.</h1>
              <div class="card-wrapper-text">
                <h2>{{ $t('delivery_to_city') }}</h2>
                <p>{{ $t('delivery_to_city_text') }}</p>
              </div>
            </div>
          </v-card>
        </v-col>
      </v-row>
    </v-card>
  </v-container>
</template>

<script>
export default {
  name: 'IndexPage',
}
</script>
<style scoped>
.card-wrapper{
  padding: 2rem;
  color: white;
  font-size: 1.3rem;
}
.card-wrapper h1{
  font: bold 2.5rem 'Roboto', sans-serif;
  color: white;
}

.card-wrapper-text{
  position: absolute;
  bottom: 0;
  width: 35rem;
}
</style>
