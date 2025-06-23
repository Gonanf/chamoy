<template>

    <v-app-bar :elevation="2">
        <template v-slot:prepend>
        <v-btn icon="mdi-pizza" @click="$router.push('/')">
        </v-btn>
    </template>
    <v-app-bar-title>Chamoy: Pizzas modernas</v-app-bar-title>
    <template v-slot:append>
        <v-btn append-icon="mdi-help" @click="$router.push('/consultas')">Reclamos/Consultas</v-btn>
    <v-btn append-icon="mdi-cart" @click="$router.push('/#prod')">Productos</v-btn>
    </template>
    </v-app-bar>
</template>