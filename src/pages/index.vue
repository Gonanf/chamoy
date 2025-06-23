<template>
  <v-carousel >
    <v-carousel-item src="@/assets/pizza_c2.jpg" cover></v-carousel-item>

    <v-carousel-item src="@/assets/pizza_c1.jpg" cover></v-carousel-item>

    <v-carousel-item src="@/assets/pizza_c3.jpg" cover></v-carousel-item>
  </v-carousel>
  <br>
  <v-row id="prod">
    <v-col cols="4">
      <v-card variant="elevated">
        <v-img height="200px" src="@/assets/napolitana.jpg" cover></v-img>
        <v-card-title>Pizza Napolitana</v-card-title>
        <v-card-subtitle>Pizza clasica italiana</v-card-subtitle>
        <v-card-text>Pizza de massa tierna con bordes altos</v-card-text>
        <v-card-text style="color: seagreen;">$1000</v-card-text>
        <v-card-actions>
          <v-btn  rounded="m" base-color="indigo-darken-3" variant="elevated" ripple @click="$router.push('/comprar?img=napolitana&tipo=Pizza+Napolitana')">Comprar</v-btn>
        </v-card-actions>
      </v-card>
    </v-col>

    <v-col cols="4">
      <v-card variant="elevated">
        <v-img height="200px" src="@/assets/new_york.jpg" cover></v-img>
        <v-card-title>Pizza Estilo New York</v-card-title>
        <v-card-subtitle>Originado en italia, se translada a las tiendas de pizzas rapidas de estados unidos</v-card-subtitle>
        <v-card-text>Pizza extremadamente delgada</v-card-text>
        <v-card-text style="color: seagreen;">$1000</v-card-text>
        <v-card-actions>
          <v-btn  rounded="m" base-color="indigo-darken-3" variant="elevated" ripple @click="$router.push('/comprar?img=new_york&tipo=Pizza+Estilo+New+York')">Comprar</v-btn>
        </v-card-actions>
      </v-card>
    </v-col>

    <v-col cols="4">
      <v-card variant="elevated">
        <v-img height="200px" src="@/assets/margarita.jpg" cover></v-img>
        <v-card-title>Pizza Margarita</v-card-title>
        <v-card-subtitle>Pizza Napolitana con albahaca, sal y aceite </v-card-subtitle>
        <v-card-text>Pizza de massa tierna y bordes altos</v-card-text>
        <v-card-text style="color: seagreen;">$1000</v-card-text>
        <v-card-actions>
          <v-btn  rounded="m" base-color="indigo-darken-3" variant="elevated" ripple @click="$router.push('/comprar?img=margarita&tipo=Pizza+Margarita')">Comprar</v-btn>
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
</template>

<script setup>
//
</script>
