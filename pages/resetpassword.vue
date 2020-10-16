<template>
  <v-app>
    <v-main>
      <v-container>
        <v-row align="center" justify="center" no-gutters>
          <v-col cols="12" sm="6" md="6" class="pt-6 pb-6">
            <v-card class="evelation-12 card">
              <v-row>
                <v-col md="6">
                  <v-card-title class="blue--text">Reset Password</v-card-title>
                </v-col>
                <v-col md="2" class="ml-auto"> </v-col>
              </v-row>

              <v-card-text>

                  
                  
                <v-form ref="form" v-model="valid" lazy-validation>

                   
                 

                  <v-text-field
                    v-model="newpassword"
                    :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
                    :rules="newpasswordRules"
                    :type="show1 ? 'text' : 'newpassword'"
                    name="input-10-1"
                    placeholder="••••••••"
                    label="New Password"
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
                    v-model="confirmnewpassword"
                    :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
                    :rules="confirmnewpassworddRules"
                    :type="show1 ? 'text' : 'confirmnewpassword'"
                    name="input-10-1"
                    placeholder="••••••••"
                    label="Confirm New Password"
                    auto-grow
                    outlined
                    rows="1"
                    row-height="7"
                    hint="At least 8 characters"
                    counter
                    @click:append="show1 = !show1"
                    required
                  ></v-text-field>
                  

                  
                  <v-row>
                    <v-col cols="12" sm="6">
                      <v-btn
                        :disabled="!valid"
                        color="success"
                        class="mr-4"
                        @click="login"
                      >
                        Reset Password
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
    newpassword: "",
    confirmnewpassword:"",

    email: "",
    
    newpasswordRules: [
      v => !!v || "New Password is required",
      v => v.length >= 8 || "Min 8 characters"
    ],
     
     confirmnewpassworddRules: [
      v => !!v || "Confirm New Password is required",
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
