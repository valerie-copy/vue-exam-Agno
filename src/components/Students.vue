<template>
  <section>
    <h2>Students</h2>

    <h3>Names  (array)</h3>
    <ul>
      <li v-for="(n, idx) in names" :key="'n-'+idx">{{ n }}</li>
    </ul>

    <div style="margin: 12px 0;">
      <button @click="showList = !showList">
        {{ showList ? "Hide" : "Show" }} Detailed List
      </button>
    </div>

    <ul v-if="showList">
      <li
        v-for="(s, idx) in students"
        :key="'s-'+idx"
        :class="{ highlight: s.score >= 90 }"
      >
        {{ s.name }} — Score: {{ s.score }}
      </li>
    </ul>

    <p>Passing Students: {{ passingCount }}</p>
  </section>
</template>

<script>
export default {
  name: "Students",
  data() {
    return {
      names: ["Kara Savanna Sajol", "Joe Marie Abapo", "Kyle Elle", "Johnna Maeghan Boligao", "Eunilyn Carman", "CJ Dumayaca"],

      showList: true,
      students: [
        { name: "Kara Savanna Sajol",score: 82 },
        { name: "Joe Marie Abapo", score: 73 },
        { name: "Kyle Elle", score: 92 },
        { name: "Johnna Maeghan Boligao",score: 85 },
        { name: "Eunilyn Carman",score: 96 },
        { name: "CJ Dumayaca",score: 94 },
      ],
    };
  },
  computed: {
    passingCount() {
      return this.students.filter(s => s.score >= 70).length;
    },
  },
};
</script>

<style scoped>
.highlight {
  color: green;
  font-weight: bold;
}
</style>
