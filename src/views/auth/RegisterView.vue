<script setup>
import AppLayout from '@/components/layout/AppLayout.vue'
import RegisterForm from '@/components/auth/RegisterForm.vue'
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
                src="/images/logocq.jpg"
                :width="mobile ? '75%' : '25%'"
              ></v-img>
              <h3 class="font-weight-black">Campus Quest</h3>
              <p>Registration Form</p>
            </v-card-title>
            <v-card-text class="bg-surface-light pt-4">
              <v-divider class="my-5"></v-divider>
              <RegisterForm></RegisterForm>
              <v-divider class="my-5"></v-divider>

              <h5 class="text-center">
                Already have account? <RouterLink to="/">Click here to Login</RouterLink>
              </h5>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </template>
    <v-row>
      <v-col cols="12" md="6" class="mx-auto">
        <v-card
          class="mx-auto mt-16"
          prepend-icon="mdi-account-plus"
          subtitle="Register"
          image="/images/bg-card.jpg"
          elevation="24"
        >
          <template v-slot:title>
            <span class="font-weight-black">Campus Quest</span>
          </template>

          <v-card-text class="bg-surface-light pt-4">
            <v-form fast-fail @submit.prevent>
              <v-text-field label="Firstname" variant="outlined"></v-text-field>

              <v-text-field label="Lastname" variant="outlined"></v-text-field>

              <v-text-field label="Email" variant="outlined"></v-text-field>

              <v-text-field label="Password" type="password" variant="outlined"></v-text-field>

              <v-text-field
                label="Password Confirmation"
                type="password"
                variant="outlined"
              ></v-text-field>

              <v-btn class="mt-2" type="submit" block>Submit</v-btn>
            </v-form>

            <v-divider class="my-5"></v-divider>

            <h5 class="text-center">
              Already have account?
              <RouterLink class="text-deep-orange-lighten-1 font-weight-black" to="/"
                >Click here to Login</RouterLink
              >
            </h5>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </AppLayout>
</template>
