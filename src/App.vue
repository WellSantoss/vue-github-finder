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
              v-model="user"
              @keyup.enter="fetchUser"
              label="Perfil do GitHub"
              outlined
              dense
            ></v-text-field>

            <v-btn @click="fetchUser" depressed color="primary">
              Pesquisar
            </v-btn>
          </v-col>
        </v-col>
      </v-row>

      <template v-if="githubInfo" cols="12">
        <UserProfile :user="githubInfo" />

        <v-divider class="mb-6"></v-divider>

        <h2 class="text-center mb-6">
          Repositórios ({{ githubInfo.public_repos }})
        </h2>
        <v-row v-if="reposInfo" justify="center">
          <template cols="12" v-for="repo in reposInfo">
            <UserRepos :repos="repo" :key="repo.id" />
          </template>
        </v-row>
      </template>
    </v-container>
  </v-app>
</template>

<script>
import UserProfile from "./components/UserProfile.vue";
import UserRepos from "./components/UserRepos.vue";

export default {
  name: "App",
  data: () => ({
    user: null,
    githubInfo: null,
    reposInfo: null,
  }),

  methods: {
    fetchUser() {
      fetch(`https://api.github.com/users/${this.user}`)
        .then((r) => r.json())
        .then((r) => {
          console.log(r.repos_url);
          this.githubInfo = r;
          this.fetchRepos(r.repos_url);
        });
    },
    fetchRepos(login) {
      fetch(login)
        .then((r) => r.json())
        .then((r) => {
          this.reposInfo = r;
        });
    },
  },

  components: {
    UserProfile,
    UserRepos,
  },
};
</script>
