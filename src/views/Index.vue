<template>
  <div class="Index">
    <div v-for="student for students">
      <h4> {{ student.first_name }}</h4>
      <h4> {{ student.last_name }}</h4>
    </div>
  </div>
</template>

<style>
</style>

<script>
  var axios = require('axios');

export default {
  data: function() {
    return {
           students: [],

    };
  },
  created: function() {
    axios
    .get("http://localhost:3000/api/students")
    .then(response => {
      this.students = response.data;
    });
  },
  methods: {},
  computed: {}
};
</script>