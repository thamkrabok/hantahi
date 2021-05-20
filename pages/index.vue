<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <v-card>
        <v-card-title class="headline center">
          <span>Call me Pope First</span>
        </v-card-title>
        <v-card-text class="center">
          <v-form ref="form" v-model="valid" lazy-validation>
            <v-text-field
              v-model="username"
              :rules="usernameRules"
              label="username"
              required
            ></v-text-field>

            <v-text-field
              v-model="pass"
              :rules="passRules"
              label="password"
              required
            ></v-text-field>

            <v-btn
              :disabled="!valid"
              color="success"
              class="mr-4"
              @click="validate"
            >
              Validate
            </v-btn>

            <v-btn color="error" class="mr-4" @click="reset">
              Reset Form
            </v-btn>

            <v-btn color="warning" @click="resetValidation">
              Reset Validation
            </v-btn>
          </v-form>
        </v-card-text>
        <v-card-actions>
          <v-btn
            class="mb-auto mt-5 mx-auto"

            color="#DF4A32"
            width="290"
            height="50"
            @click="login()"
          >
            <span class="size-20" style="text-transform: none;color: white;"
              >Login</span
            >
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  data() {
    return {
      valid: true,
      username: "",
      usernameRules: [
        v => !!v || "username is required",
        v => /.+@.+\..+/.test(v) || "username must be valid"
      ],
      pass: "",
      passRules: [
        v => !!v || "password is required",
        v => (v && v.length < 8) || "password must be less than 8 characters"
      ],
    };
  },
  methods: {
    login() {
      this.$router.push(`/home`);
    },
    validate() {
      this.$refs.form.validate();
    },
    reset() {
      this.$refs.form.reset();
    },
    resetValidation() {
      this.$refs.form.resetValidation();
    }
  }
};
</script>

<style scoped>
.center {
  align-items: center;
  justify-content: center;
}
</style>
