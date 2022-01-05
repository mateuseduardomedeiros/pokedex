<template>
  <v-app>
    <v-dialog hide-overlay :transition="false" v-model="loading" fullscreen>
      <v-container fluid class="d-flex">
        <v-progress-circular
          class="d-flex load"
          :size="80"
          color="red"
          indeterminate
        />
      </v-container>
    </v-dialog>
    <Nav @carregarGeracao="loadGeracao($event)" />
    <v-main class="bg-img">
      <v-container>
        <v-row>
          <v-col
            cols="12"
            lg="4"
            md="6"
            sm="12"
            v-for="pokemon in pokemons"
            :key="pokemon.id"
          >
            <Card
              :pokeName="pokemon.name"
              :pokeId="pokemon.id"
              :pokeSprite="
                pokemon.sprites.versions['generation-vi'][
                  'omegaruby-alphasapphire'
                ].front_default
              "
              :pokeTypes="pokemon.types"
            />
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import Card from "./components/Card.vue";
import Nav from "./components/Nav.vue";
export default {
  name: "App",
  components: {
    Card,
    Nav,
  },
  mounted() {
    this.loadPokemons(this.generations.i.limit, this.generations.i.offset);
  },
  data() {
    return {
      loading: false,
      generations: {
        i: { limit: 151, offset: 0 },
        ii: { limit: 100, offset: 151 },
        iii: { limit: 135, offset: 251 },
        iv: { limit: 107, offset: 386 },
        v: { limit: 156, offset: 493 },
        vi: { limit: 72, offset: 649 },
      },
      pokemons: [],
    };
  },
  methods: {
    async loadGeracao(geracao) {
      await this.loadPokemons(
        this.generations[geracao].limit,
        this.generations[geracao].offset
      );
    },
    async auxLoadPokemons(name) {
      try {
        const { data } = await this.$axios.get(`pokemon/${name}`);
        return data;
      } catch (error) {
        console.log(error);
      }
    },
    async loadPokemons(limit, offset) {
      this.pokemons = []
      try {
        this.loading = true;
        const { data } = await this.$axios.get(
          `pokemon?limit=${limit}&offset=${offset}`
        );
        const promisePokemons = data.results.map(
          async (item) => await this.auxLoadPokemons(item.name)
        );
        this.pokemons = await Promise.all(promisePokemons);
        this.loading = false;
      } catch (error) {
        console.log(error);
      }
    },
  },
};
</script>
<style>
*,
*::after,
*::before {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Open Sans", sans-serif;
}
.bg-img {
  background-image: linear-gradient(
      0deg,
      rgba(255, 255, 255, 0.75),
      rgba(255, 255, 255, 0.75)
    ),
    url("./assets/background.jpg") !important;
  background-repeat: repeat;
}
.load {
  margin-left: auto;
  margin-right: auto;
  margin-top: 20rem;
  display: block;
}
</style>
