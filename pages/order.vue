<template>
  <v-container class="d-flex justify-center mt-15 mb-15">
    <v-card outlined rounded class="pa-5 form-order" width="75rem">
      <h2 class="mb-5">{{$t('complete_question')}}</h2>
      <v-alert v-if="errors" type="error">
        <div v-for="(v, k) in errors" :key="k">
          <p v-for="error in v" :key="error" class="text-sm">
            {{ error }}
          </p>
        </div>
      </v-alert>
      <v-row>
        <v-col cols="12" sm="6" lg="6" md="6">
          <v-text-field outlined  v-model="dataFields.full_name" :label="$t('full_name')" dense></v-text-field>
          <v-text-field outlined v-model="dataFields.contacts" :label="$t('contacts')" dense :hint="$t('instagram_phone_number')"></v-text-field>
          <v-text-field outlined v-model="dataFields.brand" :label="$t('brands')" dense></v-text-field>
          <v-text-field outlined v-model="dataFields.model" :label="$t('model')" dense></v-text-field>
          <v-text-field outlined v-model="dataFields.year" :label="$t('years')" dense></v-text-field>
          <v-select outlined v-model="dataFields.engine_type" :label="$t('type_engine')" :items="engineType" dense></v-select>
          <v-text-field  outlined v-model="dataFields.engine_capacity"  :label="$t('volume_engine')" dense></v-text-field>
        </v-col>

        <v-col cols="12" sm="6" lg="6" md="6">
          <v-select outlined v-model="dataFields.transmission" :label="$t('transmission')" :items="transmissionType" dense></v-select>
          <v-select outlined v-model="dataFields.drive" :label="$t('drive')" :items="driveType" dense></v-select>
          <v-text-field outlined v-model="dataFields.horse_power" :label="$t('horse_power')" dense></v-text-field>
          <v-select outlined v-model="dataFields.car_body" :label="$t('car_body')" :items="carBodyType" dense></v-select>
          <v-select outlined v-model="dataFields.wheel" :label="$t('wheel')" :items="wheelType" dense></v-select>
          <v-select outlined v-model="dataFields.quality" :label="$t('quality')" :items="quality" dense></v-select>
          <v-btn outlined @click.prevent="sendRequest" color="primary">{{$t('send_request')}}</v-btn>

        </v-col>
      </v-row>
    </v-card>
  </v-container>
</template>

<script>
export default {
  name: 'OrderPage',
  data () {
    return {
      dataFields: {
        full_name: '',
        contacts: '',
        brand: '',
        model: '',
        year: '',
        engine_type: '',
        engine_capacity: '',
        transmission: '',
        drive: '',
        horse_power: '',
        car_body: ''
      },
      errors: null,
      engineType: [
        { text: this.$t('petrol') },
        { text: this.$t('diesel') },
        { text: this.$t('hybrid') },
        { text: this.$t('electro_engine')},
      ],
      transmissionType: [
        { text: this.$t('automat')},
        { text: this.$t('mechanic') },
        { text: this.$t('variator') },
        { text: this.$t('robot')}
      ],
      driveType: [
        { text: this.$t('forward') },
        { text: this.$t('backward') },
        { text: this.$t('full_drive') },
      ],
      carBodyType: [
        { text: this.$t('sedan')},
        { text: this.$t('off_road')},
        { text: this.$t('hatchback')},
        { text: this.$t('universal') },
        { text: this.$t('coupe') },
        { text: this.$t('minivan') },
        { text: this.$t('micro_bus') },
        { text: this.$t('liftback') },
        { text: this.$t('van') },
        { text: this.$t('pickup') },
        { text: this.$t('cabriolet') },
      ],
      wheelType:[
        {text: this.$t('right') },
        {text: this.$t('left')},
      ],
      quality: [
        {text: this.$t('used')},
        {text: this.$t('new')},
        {text: this.$t('with_damage')},
        {text: this.$t('recovered')},
      ]
    }
  },
  methods: {
    sendRequest () {
      this.$axios.post('http://localhost:8000/api/orders', this.dataFields)
        .then(this.redirectSuccess)
        .catch(error => {
        this.errors = error.response.data.errors;
      });
    },
    redirectSuccess () {
      this.$router.push('/success')
    }
  }

}
</script>
