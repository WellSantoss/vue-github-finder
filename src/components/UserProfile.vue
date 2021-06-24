<template>
  <v-row>
    <v-col cols="12" class="mx-auto" align="center">
      <v-card max-width="374" align="center" elevation="0">
        <v-avatar size="120">
          <img
            src="https://avatars.githubusercontent.com/u/75996494?v=4"
            alt="Foto de perfil"
          />
        </v-avatar>

        <v-card-title align="center" style="justify-content: center">
          Wellington
        </v-card-title>

        <v-card-text>
          <div><a href="#">@WellSantoss</a></div>

          <div>Desenvolvedor Front-End</div>
        </v-card-text>

        <v-divider></v-divider>

        <v-card-text>
          <p>
            <v-icon>mdi-map-marker</v-icon>Birigui - SP
            <v-icon class="ml-8">mdi-account-multiple</v-icon> 7 seguidores - 5
            seguindo
          </p>
        </v-card-text>
      </v-card>
      <v-divider></v-divider>
      <UserRepos />
    </v-col>
  </v-row>
</template>

<script>
import UserRepos from "./UserRepos.vue";

export default {
  name: "UserProfile",
  components: {
    UserRepos,
  },
};
</script>
