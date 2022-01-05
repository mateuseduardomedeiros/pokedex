<template>
  <v-card dark tile>
    <v-card-text>
      <v-row>
        <v-col cols="12" lg="6" md="6" sm="12">
          <v-container class="d-flex justify-center justify-sm-center">
           <img src="@/assets/logo.png" width="150" height="auto" alt="Pokemon Logo">
            <!-- <v-img
              eager
              alt="Logo Pokemón"
              class="shrink"
              src="@/assets/logo.png"
              transition="scale-transition"
              :contain="true"
              max-width="150"
              height="auto"
            /> -->
          </v-container>
        </v-col>
        <v-col cols="12" lg="6" md="6" sm="12">
          <v-container class="d-flex justify-end justify-sm-center pa-5">
            <nav id="menu">
              <ul>
                <li>
                  <v-btn
                    @click="carregarGeracao('i')"
                    class="white black--text ma-1"
                    icon
                    elevation="3"
                    >I</v-btn
                  >
                </li>
                <li>
                  <v-btn
                    @click="carregarGeracao('ii')"
                    class="white black--text ma-1"
                    icon
                    elevation="3"
                    >II</v-btn
                  >
                </li>
                <li>
                  <v-btn @click="carregarGeracao('iii')" class="white black--text ma-1" icon elevation="3"
                    >III</v-btn
                  >
                </li>
                <li>
                  <v-btn @click="carregarGeracao('iv')" class="white black--text ma-1" icon elevation="3"
                    >IV</v-btn
                  >
                </li>
                <li>
                  <v-btn @click="carregarGeracao('v')" class="white black--text ma-1" icon elevation="3"
                    >V</v-btn
                  >
                </li>
                <li>
                  <v-btn @click="carregarGeracao('vi')" class="white black--text ma-1" icon elevation="3"
                    >VI</v-btn
                  >
                </li>
                <li>
                  <v-btn @click="carregarGeracao('vii')" class="white black--text ma-1" icon elevation="3"
                    >VII</v-btn
                  >
                </li>
                <li>
                  <v-btn @click="carregarGeracao('viii')" class="white black--text ma-1" icon elevation="3"
                    >VIII</v-btn
                  >
                </li>
              </ul>
            </nav>
          </v-container>
        </v-col>
      </v-row>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  name: "Nav",
  methods: {
    carregarGeracao(geracao) {
      this.$emit("carregarGeracao", geracao);
    },
  },
};
</script>

<style scoped>
#menu ul li {
  display: inline;
  font-size: 0.9rem;
  text-transform: uppercase;
  padding: 0.1rem 0.1rem;
  display: inline-block;
  color: white;
  text-decoration: none;
}

#menu ul li a:hover {
  text-shadow: 0 0 5px red;
  border-bottom: 2px solid red;
}
</style>
