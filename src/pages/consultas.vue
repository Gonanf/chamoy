<template>
    <div class="text-center">
    <h1>Consultas</h1>
        <v-form @submit.prevent="onSubmit" v-model="form">
            <v-text-field label="Nombre" prepend-icon="mdi-account" clearable :rules="[required]"></v-text-field>
            <v-text-field label="Apellido" prepend-icon="mdi-account"clearable :rules="[required]"></v-text-field>
            <v-text-field label="Email" prepend-icon="mdi-email" clearable :rules="[required]" type="email"></v-text-field>
            <v-text-field label="Razon de la consulta" prepend-icon="mdi-help" clearable :rules="[required]"></v-text-field>
            <v-btn type="submit" :disabled="!form" :loading="form_loading">Continuar</v-btn>
        </v-form>
    </div>

    <v-dialog v-model="dialog" width="auto">
        <v-card max-width="400" prepend-icon="mdi-check"
            text="Se te enviara una respuesta al Email en la medida de lo posible" title="Completado">
            <template v-slot:actions>
                <v-btn class="ms-auto" text="Ok" @click="$router.push('/')"></v-btn>
            </template>
        </v-card>
    </v-dialog>
</template>

<script setup>
import { ref } from 'vue';
const route = useRoute();

const dialog = ref(false);
const form = ref(false);
const form_loading = ref(false);

function onSubmit() {
    if (!form.value) return
    form_loading.value = true
    setTimeout(() => { form_loading.value = false; dialog.value=true; }, 2000)
}

function required(v) {
    return !!v || 'El campo tiene que ser ingresado'
}

</script>