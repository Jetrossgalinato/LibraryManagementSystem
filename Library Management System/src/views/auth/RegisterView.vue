<script setup>
import AppLayout from '@/components/layout/AppLayout.vue'
import RegisterForm from '@/components/auth/RegisterForm.vue'
</script>

<template>
  <AppLayout>
    <template #content>
      <v-container fluid
        ><v-row>
          <v-col cols="12" md="6" class="mx-auto pt-16"
            ><v-card class="mx-auto" elevation="23">
              <v-card-title class="text-center">
                <v-img class="mx-auto" src="/images/logo-favicon.png" width="25%"></v-img>
                <h3 class="font-weight-black">Library Management System</h3>
                <p class="text-subtitle-2">Register form</p>
              </v-card-title>

              <v-card-text class="bg-surface-light pt-4">
                <RegisterForm></RegisterForm>
                <v-divider class="my-5"></v-divider>

                <h5 class="text-center">
                  Already have an account?
                  <RouterLink class="text-deep-orange-lighten-1 font-weight-black" to="/"
                    >Click here to Login</RouterLink
                  >
                </h5>
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </template>
  </AppLayout>
</template>
