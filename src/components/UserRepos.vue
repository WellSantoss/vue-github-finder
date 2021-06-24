<template>
  <v-card width="350" class="ma-3">
    <v-card-title>{{ repos.name }}</v-card-title>

    <v-card-subtitle>{{ repos.description }}</v-card-subtitle>

    <v-card-actions>
      {{ repos.language }}
      <v-icon class="ml-5 mr-2">mdi-star-outline</v-icon
      >{{ repos.stargazers_count }}
      <v-icon class="ml-5 mr-2">mdi-source-branch</v-icon>{{ repos.forks }}
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  name: "UserRepos",
  props: ["repos"],
};
</script>
