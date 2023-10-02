<template>
  <div class="container contact-form">
    <h1>Contact Me</h1>
    <form @submit.prevent="submitForm">
      <div class="form-group">
        <label for="name">Name</label>
        <input type="text" id="name" v-model="name" required />
      </div>
      <div class="form-group">
        <label for="email">Email</label>
        <input type="email" id="email" v-model="email" required />
      </div>
      <button type="submit">Submit</button>
      <p v-if="isSubmitted">Thank you for your submission!</p>
      <p v-if="hasError">Please fill in both name and email.</p>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "",
      email: "",
      isSubmitted: false,
      hasError: false,
    };
  },
  methods: {
    submitForm() {
      if (this.name && this.email) {
        this.isSubmitted = true;
        this.hasError = false;
      } else {
        this.isSubmitted = false;
        this.hasError = true;
      }
    },
  },
};
</script>

<style scoped>
</style>
