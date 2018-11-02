<template>
  <div class="show">
    <h1>{{ student.first_name }} {{student.last_name}} </h1>
    <br>
    

    <ol>
      <li> {{student.github_url}} </li>
      <li> {{student.email}} </li>
    </ol>
  </div>

</template>

<script>
var axios = require('axios');
export default {
  data: function() {
    return {
      student:{
          first_name: "",
          last_name: "",
          github: "",
          email: "",
          capstones: []
        }
    };
  },
  created: function() {
    axios
    .get("/api/students/" + this.$route.params.id)
    .then(response => {
      this.student = response.data;
    });
  },
  methods: {},
  computed: {}
};
</script>