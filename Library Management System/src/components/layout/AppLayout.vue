<script setup>
import { ref } from 'vue'

const theme = ref(localStorage.getItem('theme') ?? 'light')

function onClick() {
  theme.value = theme.value === 'light' ? 'dark' : 'light'
  localStorage.setItem('theme', theme.value)
}
</script>

<template>
  <v-responsive class="border rounded">
    <v-app :theme="theme">
      <v-app-bar
        class="px-3"
        :color="theme === 'light' ? 'grey-lighten-2' : 'grey-darken-3'"
        border
      >
        <v-spacer></v-spacer>

        <!-- Update the button color based on the theme -->
        <v-btn
          :icon="theme === 'light' ? 'mdi-weather-sunny' : 'mdi-weather-night'"
          variant="elevated"
          :style="{ backgroundColor: theme === 'light' ? '#F7971D' : '#F7971D', color: 'white' }"
          slim
          @click="onClick"
        ></v-btn>
      </v-app-bar>

      <v-main>
        <slot name="content"></slot>
      </v-main>

      <v-footer
        class="font-weight-bold"
        :color="theme === 'light' ? 'grey-lighten-2' : 'grey-darken-3'"
        elevation="24"
        border
        app
      >
        2024 - Library Management System
      </v-footer>
    </v-app>
  </v-responsive>
</template>
