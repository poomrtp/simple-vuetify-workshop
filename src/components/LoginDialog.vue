<template>
  <v-dialog v-model="dialog" width="500" persistent>
    <template v-slot:activator="{ on, attrs }">
      <v-btn text color="white" v-on="on" v-bind="attrs">
        <v-icon>mdi-login</v-icon>
        Login
      </v-btn>
    </template>
    <v-card>
      <v-card-title class="text-h5 grey lighten-2">
        Login
        <v-spacer></v-spacer>
        <v-btn text color="red" rounded icon @click="closeDialog">
          <v-icon>mdi-close</v-icon>
        </v-btn>
      </v-card-title>
      <v-form ref="form">
        <v-container>
          <v-text-field v-model="email" :rules="emailRules" label="E-mail" required></v-text-field>
          <v-text-field
            v-model="password"
            type="password"
            :rules="passwordRules"
            label="Password"
            required
          ></v-text-field>
        </v-container>
      </v-form>
      <v-divider></v-divider>
      <v-card-actions>
        <v-btn color="primary" text @click="closeDialog">Register</v-btn>
        <v-spacer></v-spacer>
        <v-btn color="primary" @click="closeDialog">Login</v-btn>
      </v-card-actions>
    </v-card>
  </v-dialog>
</template>
<script>
export default {
  name: 'LoginDialog',
  data() {
    return {
      dialog: false,
      email: '',
      password: '',
      emailRules: [
        (v) => !!v || 'E-mail is required',
        (v) => /.+@.+/.test(v) || 'E-mail must be valid'
      ],
      passwordRules: [
        (v) => !!v || 'Password is required',
        (v) => v.length >= 4 || 'Name must be more than 4 characters'
      ]
    }
  },
  methods: {
    closeDialog() {
      this.$refs.form.resetValidation()
      this.dialog = false
    }
  }
}
</script>
