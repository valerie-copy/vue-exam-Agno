<template>
  <section>
    <h2>Hello from Greeting Component</h2>

    <p>Hello, {{ username}}</p>
  </section>
</template>

<script>
import { capitalize } from "../utils.js";

export default {
  name: "Greeting",
  props: {
    username: { type: String, required: true },
  },
  data() {
    return {
      message: "hello from greeting component",
    };
  },
  computed: {
    capitalizedMessage() {
      return capitalize(this.message);
    },
  },
};
</script>