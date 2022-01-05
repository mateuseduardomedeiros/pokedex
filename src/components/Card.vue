<template>
  <v-card dark class="card" :class="pokeTypes[0].type.name" elevation="10">
    <div class="bg">
      <v-img
        eager
        class="pokeball"
        height="auto"
        width="150"
        src="@/assets/pokeball.png"
      />
      <v-card-title class="pb-0">
        <p class="mb-1">#{{ String(pokeId).padStart(4, "0") }}</p>
      </v-card-title>
      <v-card-title class="pt-0">
        <h1>{{ pokeName }}</h1>
      </v-card-title>
      <v-card-subtitle>
        <div class="types">
          <Type
            class="mr-1"
            v-for="type in pokeTypes"
            :key="type.slot"
            :type="type.type.name"
          />
        </div>
      </v-card-subtitle>
      <v-card-text>
        <v-container>
          <v-img
            class="poke-img"
            width="auto"
            height="auto"
            :src="pokeSprite"
          />
        </v-container>
      </v-card-text>
    </div>
  </v-card>
</template>

<script>
import Type from "./Type.vue";
export default {
  name: "Card",
  components: {
    Type,
  },
  props: {
    pokeName: String,
    pokeId: Number,
    pokeSprite: String,
    pokeTypes: Array,
  },
};
</script>

<style scoped>
.card {
  position: relative;
  margin: 0.5rem 0.1rem;
}
.bg {
  background-color: rgba(230, 230, 230, 0.5);
  padding: 1.8rem;
}
.types {
  z-index: 2 !important;
}
.pokeball {
  z-index: 0;
  position: absolute;
  right: 5%;
  top: 22%;
  filter: invert(100%) opacity(10%);
  overflow: hidden;
}
p {
  font-size: 1.5rem;
  line-height: 0.9rem;
  font-family: "Roboto";
}
h1 {
  font-size: 1.8rem;
  overflow: hidden;
  white-space: nowrap;
  padding-bottom: 0.625rem;
  text-transform: capitalize;
}
.poke-img {
  position: absolute;
  top: 20%;
  right: 10%;
  overflow: hidden;
}
.normal {
  background-color: #a9ac99 !important;
}
.fire {
  background-color: #ff001d !important;
}
.water {
  background-color: #008bff !important;
}
.electric {
  background-color: #ffd129 !important;
}
.grass {
  background-color: #15db51 !important;
}
.ice {
  background-color: #1bcbff !important;
}
.fighting {
  background-color: #d8625f !important;
}
.poison {
  background-color: #bf339a !important;
}
.ground {
  background-color: #e3c051 !important;
}
.flying {
  background-color: #8f86ff !important;
}
.psychic {
  background-color: #ff0099 !important;
}
.bug {
  background-color: #9cc616 !important;
}
.rock {
  background-color: #bdaf64 !important;
}
.ghost {
  background-color: #7053bc !important;
}
.dragon {
  background-color: #8b35f0 !important;
}
.dark {
  background-color: #382c28 !important;
}
.steel {
  background-color: #aba8bb !important;
}
.fairy {
  background-color: #ff7bef !important;
}
</style>
