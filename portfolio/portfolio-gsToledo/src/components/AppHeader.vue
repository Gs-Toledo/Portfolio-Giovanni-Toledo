<template>

  <v-app-bar :elevation="2">

    <template #prepend>
      <v-app-bar-nav-icon />
    </template>

    <v-app-bar-title>

      <v-row justify="center" no-gutters>
        <v-btn
          v-for="link in links"
          :key="link"
          class="mx-2"
          rounded="xl"
          variant="text"
        >
          {{ link }}
        </v-btn>
      </v-row>

    </v-app-bar-title>

    <v-btn
      class="mdi mdi-theme-light-dark"
      density="compact"
      rounded="xl"
      size="small"
      @click="toggleTheme"
    />

  </v-app-bar>

</template>

<script lang="ts" setup>

  import { useTheme } from 'vuetify'

  const theme = useTheme()

  function toggleTheme () {
    theme.global.name.value = theme.global.current.value.dark ? 'light' : 'dark'
  }

  const links = [
    'Home',
    'Sobre',
    'Projetos',
    'Serviços',
    'Blog',
    'Fale Comigo',
  ]

</script>
