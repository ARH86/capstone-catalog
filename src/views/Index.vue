<template>
  <div class="Index">
    <div class="container">
      <div v-for="student in students">
        <div class="row">
          <div class="column">
            <h4>Name: {{ student.first_name }} {{ student.last_name }} </h4>
            <h4>Capstone: {{ student.capstone.name }}</h4>
            <h4> {{ student.capstone.screenshot }}</h4>
              <form action="">
                <button id="" onclick="function()" type="submit" value="">More Info</button>
              ca</form>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
  {
     box-sizing: border-box;
 }

 
 .column {
     float: left;
     width: 33.33%;
     padding: 10px;
     height: 300px; 
 }


 .row:after {
     content: "";
     display: table;
     clear: both;
 }

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
    .get("/api/students")
    .then(response => {
      this.students = response.data;
    });
  },
  methods: {},
  computed: {}
};
</script>