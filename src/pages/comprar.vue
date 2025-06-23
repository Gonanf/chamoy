<template>
  <v-card height="100%">

    <div class="d-flex flex-no-wrap justify-space-between " style="height: 100%;">
        <v-img src="@/assets/napolitana.jpg" style="height: 100%;flex-grow: 1;" cover></v-img>
      <div style="flex-grow: 1;">
        <v-card-title class="text-h5">
          {{$route.query.tipo}}
        </v-card-title>

        <v-card-subtitle style="color: seagreen;">$1000</v-card-subtitle>

        <v-stepper :items="['Paso 1', 'Paso 2', 'Paso 3']" hide-actions v-model="step">
  <template v-slot:item.1>
    <v-card title="Ingresar datos" flat>
      <v-form @submit.prevent="onSubmit" v-model="form">
      <v-text-field label="Nombre" prepend-icon="mdi-account" clearable :rules="[required]"></v-text-field>
      <v-text-field label="Numero de tarjeta" prepend-icon="mdi-card-account-details" clearable :rules="[required]"></v-text-field>
      <v-text-field label="Fecha de vencimiento" prepend-icon="mdi-calendar-account" clearable :rules="[required]"></v-text-field>
      <v-text-field label="Codigo de seguridad" prepend-icon="mdi-numeric" clearable :rules="[required]"></v-text-field>
      <v-text-field label="Direccion" prepend-icon="mdi-map-marker-account" clearable :rules="[required]"></v-text-field>
      <v-btn type="submit" 
      :disabled="!form"
          :loading="form_loading"
          >Continuar</v-btn>
    </v-form>
    </v-card>
  </template>

  <template v-slot:item.2>
    <v-card title="Comprar" flat>
      <v-btn
          @click="confirmar"
          :loading="form_loading"
          >Confirmar</v-btn>
    </v-card>
  </template>

  <template v-slot:item.3>
    <v-card title="Listo!" flat class="text-center">
      <v-icon
            class="mb-6"
            color="success"
            icon="mdi-check-circle-outline"
            size="128"
          ></v-icon>

          <div class="text-h4 font-weight-bold">Se le enviara el pedido a su direccion en proximamente</div>
          <v-btn @click="$router.push('/')">Salir</v-btn>
    </v-card>
  </template>
</v-stepper>
      </div>


    </div>

  </v-card>
</template>

<script setup>
import { ref, computed } from 'vue';
import { useRoute } from 'vue-router'
const route = useRoute();
    var step = ref(1);
    const form = ref(false);
    const form_loading = ref(false);
    
    function onSubmit () {
    if (!form.value) return
    form_loading.value = true
    setTimeout(() => {form_loading.value=false;step.value++;}, 2000)
  }

  function required (v) {
    return !!v || 'El campo tiene que ser ingresado'
  }

  function confirmar()
  {
    form_loading.value = true
    setTimeout(() => {form_loading.value=false;step.value++;}, 2000)
  }

</script>