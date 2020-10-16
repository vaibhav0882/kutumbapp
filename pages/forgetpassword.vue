<template>
  <v-app>
    <v-main>
      <v-container>
        <v-row align="center" justify="center" no-gutters>
          <v-col cols="12" sm="6" md="6" class="pt-6 pb-6">
            <v-card class="evelation-12 card">
              <v-row>
                <v-col md="6">
                  <v-card-title class="blue--text">Forget Password</v-card-title>
                </v-col>
                <v-col md="2" class="ml-auto"> </v-col>
              </v-row>

              <v-card-text>

                  
                  
                <v-form ref="form" v-model="valid" lazy-validation>

                   
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
                     <div>
                      I Remember My Password<nuxt-link to="/">
                        Login</nuxt-link
                      >
                    </div>
                  
                  

                  
                  <v-row>
                    <v-col cols="12" sm="6">
                         <a href='/resetpassword'>
                      <v-btn
                        :disabled="!valid"
                        color="success"
                        class="mr-4"
                       
                      >
                        Reset My Password
                      </v-btn>
                         </a>
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
    email: "",
   

    email: "",
    emailRules: [
      v => !!v || "E-mail is required",
      v => /.+@.+\..+/.test(v) || "E-mail must be valid"
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
