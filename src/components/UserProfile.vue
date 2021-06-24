<template>
  <v-row>
    <v-col cols="12" class="mx-auto" align="center">
      <v-card max-width="374" align="center" elevation="0">
        <v-avatar size="120">
          <img :src="user.avatar_url" alt="Foto de perfil" />
        </v-avatar>

        <v-card-title align="center" style="justify-content: center">
          {{ user.name }}
        </v-card-title>

        <v-card-text>
          <div>
            <a :href="'https://github.com/' + user.login" target="_blank"
              >@{{ user.login }}</a
            >
          </div>

          <div>{{ user.bio }}</div>
        </v-card-text>

        <v-divider></v-divider>

        <v-card-text>
          <p>
            <v-icon>mdi-map-marker</v-icon>{{ user.location }}
            <v-icon class="ml-2">mdi-account-multiple</v-icon>
            {{ user.followers }} seguidores | {{ user.following }}
            seguindo
          </p>
        </v-card-text>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: "UserProfile",
  props: ["user"],
};
</script>
