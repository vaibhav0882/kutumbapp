<template>
  <v-app>
    <v-main>
      <v-container>
        <v-row align="center" justify="center" no-gutters>
          <v-col cols="12" sm="6" md="6" class="pt-6 pb-6">
            <v-card class="evelation-12 card">
              <v-row>
                <v-col md="4">
                  <v-card-title class="blue--text">Register</v-card-title>
                </v-col>
                <v-col md="2" class="ml-auto"> </v-col>
              </v-row>

              <v-card-text>

                  
                  
                <v-form ref="form" v-model="valid" lazy-validation>

                    <v-text-field
                    v-model="name"
                    :rules="nameRules"
                    label="User Name"
                    auto-grow
                    outlined
                    rows="1"
                    row-height="7"
                    required
                  ></v-text-field>
                  <v-text-field
                    v-model="email"
                    :rules="emailRules"
                    label="E-mail"
                    auto-grow
                    outlined
                    rows="1"
                    row-height="7"
                    required
                  ></v-text-field>

                  <v-text-field
                    v-model="password"
                    :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
                    :rules="passwordRules"
                    :type="show1 ? 'text' : 'password'"
                    name="input-10-1"
                    placeholder="••••••••"
                    label="Password"
                    auto-grow
                    outlined
                    rows="1"
                    row-height="7"
                    hint="At least 8 characters"
                    counter
                    @click:append="show1 = !show1"
                    required
                  ></v-text-field>
                  <v-text-field
                    v-model="confirmpassword"
                    :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
                    :rules="confirmpassworddRules"
                    :type="show1 ? 'text' : 'confirmpassword'"
                    name="input-10-1"
                    placeholder="••••••••"
                    label="Confirm Password"
                    auto-grow
                    outlined
                    rows="1"
                    row-height="7"
                    hint="At least 8 characters"
                    counter
                    @click:append="show1 = !show1"
                    required
                  ></v-text-field>
                  <div>
                      I Remember My Password<nuxt-link to="/">
                        Login</nuxt-link
                      >
                    </div>
                  

                  
                  <v-row>
                    <v-col cols="12" sm="6">
                      <v-btn
                        :disabled="!valid"
                        color="success"
                        class="mr-4"
                        @click="login"
                      >
                        Register
                      </v-btn>
                    </v-col>
                    <v-col cols="12" sm="6">
                      <span class="font-weight-light">
                        Login with Social Accounts
                      </span>
                      <v-btn icon color="blue">
                        <v-icon>mdi-facebook</v-icon>
                      </v-btn>
                      <v-btn icon color="red">
                        <v-icon>mdi-gmail</v-icon>
                      </v-btn>
                    </v-col>
                  </v-row>
                </v-form>
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import Logo from "~/components/Logo.vue";
export default {
  components: {
    Logo
  },
  data: () => ({
    show1: false,
    valid: true,
    name: "",
    email: "",
    password: "",
    confirmpassword:"",

    email: "",
    emailRules: [
      v => !!v || "E-mail is required",
      v => /.+@.+\..+/.test(v) || "E-mail must be valid"
    ],
    passwordRules: [
      v => !!v || "Password is required",
      v => v.length >= 8 || "Min 8 characters"
    ],
      nameRules: [
      v => !!v || "Username is required",
      //v => v.length >= 8 || "Min 8 characters"
    ],
     confirmpassworddRules: [
      v => !!v || "ConfirmPassword is required",
      v => v.length >= 8 || "Min 8 characters"
    ],
    

    checkbox: false
  }),

  methods: {
    login() {
      this.$refs.form.validate();
    }
  }
};
</script>
