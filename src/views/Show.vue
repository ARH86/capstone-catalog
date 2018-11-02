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
          first_name: "George",
          last_name: "Washington",
          github: "www.github.com",
          email: "gboy94@gmail.com"
          }
      capstones:{
          name: "My Project",
          description: "This is the project description",
          url: "This is the website for where you will find the project",
          screenshot: "https://cdn-images-1.medium.com/max/1600/0*ngXgBNNdx6iiWP8q.png"
      }
    };
  },
  created: function() {
    axios
    .get("/api/students/2")
    .then(response => {
      this.student = response.data;
    });
  },
  methods: {},
  computed: {}
};
</script>