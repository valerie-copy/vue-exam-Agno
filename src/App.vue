<template>

  <main>

    <h1>Vue Prelim Exam</h1>

    <Greeting :username="user" />

    <hr style="margin: 24px 0;" />

    <Students />
  </main>
</template>



<script>
import Greeting from "./components/Greeting.vue";
import Students from "./components/Students.vue";

export default {
  name: "App",
  components: { Greeting, Students },
  data() {
    return {
      user: "Valerie Agno",
    };
  },
};
</script>
