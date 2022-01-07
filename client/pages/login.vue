<template>
  <b-container>
    <b-row>
      <b-col cols="6" class="mx-auto">
        <b-card title="Login">
          <b-button variant="primary" @click="login()">Login</b-button>
        </b-card>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
export default {
    // middleware: "guest",
  data(){
    return {
      form: {
        email: "jdoe@gmail.com",
        password: "password"
      }
    };
  },

  methods: {
    login(){
      this.$auth
        .loginWith("laravelSanctum", {
          data: this.form
        })
        .then(response => console.log(response))
        .catch(error => console.log(error));
    }
  }
};
</script>
