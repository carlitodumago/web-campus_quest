<script setup>
import AppLayout from '@/components/Layout/AppLayout.vue'
import { useDisplay } from 'vuetify'

const { mobile } = useDisplay()
</script>

<template>
  <AppLayout>
    <template #content>
      <v-row>
        <v-col cols="12" md="6" class="mx-auto">
          <v-card class="mx-auto mt-16" elevation="24">
            <v-card-title class="text-center">
              <v-img
                class="mx-auto rounded-circle"
                src="/public/images/logocq.jpg"
                :width="mobile ? '75%' : '25%'"
              ></v-img>
              <h3 class="font-weight-black">Campus Quest</h3>
              <p>Login Form</p>
            </v-card-title>

            <v-card-text class="bg-surface-light pt-4">
              <v-divider class="my-5"></v-divider>
              <v-form fast-fail @submit.prevent>
                <v-text-field label="Email" variant="outlined"></v-text-field>

                <v-text-field label="Password" type="password" variant="outlined"></v-text-field>
                <v-btn class="mt-2" type="submit" block color="primary" prepend-icon="mdi-login"
                  >Login</v-btn
                >
              </v-form>

              <v-divider class="my-5"> </v-divider>

              <h5 class="text-center">
                Don't have Account?
                <RouterLink to="/register">Click here to register</RouterLink>
              </h5>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </template>
  </AppLayout>
</template>
