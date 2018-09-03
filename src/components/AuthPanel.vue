<template>
<div class="auth-panel">
  <h1>Please {{ content }}</h1>
  <input type="email"
    name="email"
    id="email"
    placeholder="Email Address"
    v-model="email">
  <input type="password"
    name="password"
    id="password"
    placeholder="Password"
    v-model="password">
  <button @click="handleSubmit">{{ content }}</button>
</div>
</template>
<script>
export default {
  props: ["type"],
  data: function() {
    return {
      email: "",
      password: ""
    };
  },
  computed: {
    content: function() {
      if (this.type === "login") {
        return "Login";
      } else {
        return "Sign up";
      }
    }
  },
  methods: {
    handleSubmit: function() {
      const payload = {
        email: this.email,
        password: this.password
      };
      console.log("submit auth");
      console.dir(payload);
    }
  }
};
</script>
