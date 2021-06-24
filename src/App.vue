<template>
  <v-app>
    <v-container>
      <v-row>
        <v-col cols="12" align="center">
          <h1>Github Finder</h1>
          <p>Pesquise por perfis do GitHub</p>
        </v-col>

        <v-col cols="12" align="center">
          <v-col cols="6" align="center">
            <v-text-field
              label="Perfil do GitHub"
              outlined
              dense
            ></v-text-field>

            <v-btn depressed color="primary"> Pesquisar </v-btn>
          </v-col>
        </v-col>
      </v-row>
    </v-container>
    <UserProfile />
  </v-app>
</template>

<script>
import UserProfile from "./components/UserProfile.vue";

export default {
  name: "App",
  data: () => ({
    user: null,
  }),

  methods: {},

  components: {
    UserProfile,
  },
};
</script>
