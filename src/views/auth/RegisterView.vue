<script setup>
import { ref } from 'vue'

const theme = ref('light')
const showPassword = ref(false) // Ref to toggle password visibility
const showPasswordConfirmation = ref(false) // Ref for confirmation field

function onClick() {
  theme.value = theme.value === 'light' ? 'dark' : 'light'
}
</script>

<template>
  <v-responsive class="border rounded">
    <v-app :theme="theme">
      <v-app-bar class="px-3" color="grey-lighten-1">
        <v-spacer></v-spacer>

        <v-btn
          :prepend-icon="theme === 'light' ? 'mdi-weather-sunny' : 'mdi-weather-night'"
          text="Toggle Theme"
          slim
          @click="onClick"
        ></v-btn>
      </v-app-bar>

      <v-main>
        <v-container>
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

                    <v-text-field
                      label="Password"
                      :type="showPassword ? 'text' : 'password'"
                      variant="outlined"
                      :append-icon="showPassword ? 'mdi-eye-off' : 'mdi-eye'"
                      @click:append="showPassword = !showPassword"
                    ></v-text-field>

                    <v-text-field
                      label="Password Confirmation"
                      :type="showPasswordConfirmation ? 'text' : 'password'"
                      variant="outlined"
                      :append-icon="showPasswordConfirmation ? 'mdi-eye-off' : 'mdi-eye'"
                      @click:append="showPasswordConfirmation = !showPasswordConfirmation"
                    ></v-text-field>

                    <v-btn class="mt-2" type="submit" block>Submit</v-btn>
                  </v-form>

                  <v-divider class="my-5"></v-divider>

                  <h5 class="text-center">
                    Already have account? <RouterLink to="/">Click here to Login</RouterLink>
                  </h5>
                </v-card-text>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </v-main>

      <v-footer color="grey-lighten-1" border app>2024 - Campus Quest</v-footer>
    </v-app>
  </v-responsive>
</template>
