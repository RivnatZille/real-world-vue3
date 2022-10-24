<template>
  <p>Register for the event here.</p>
  <button @click="register">Register Me</button>
</template>

<script>
export default {
  name: "EventDetails",

  inject: ["GStore"],

  props: ["event"],

  methods: {
    register() {
      // Call to API
      // If registered then redirect to event details
      this.GStore.flashMessage =
        "You are successfully registered for " + this.event.title;

      setTimeout(() => {
        this.GStore.flashMessage = "";
      }, 3000);

      this.$router.push({
        name: "EventDetails",
      });
    },
  },
};
</script>

<style scoped></style>
