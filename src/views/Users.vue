<template>
  <div class="about container">
    <h1>This is an users page</h1>
<div class="">
    <div class="card  " v-for="user in users">
      <div class="card-header bg-dark text-light">
        <h2>{{ user.name }}</h2>
      </div>
      <div class="card-body">
        
          <span v-for="post in user.posts">
            <h4>{{ post.title }}</h4>
            <p>{{ post.body }}</p>
            <hr>
          </span>
         </div>
      </div>
    </div>
  </div>

 
</template>

<script>
  import axios from "axios";

  export default {
    data(){
      return {
        users: []
      }
    },
    created() {
      // fetch('http://localhost:8000/api/users')
      //   .then(response => response.json())
      //   .then(json => {
      //     this.users = json;
      //     console.log(json);
      //   });

        axios
        .get('http://localhost:8000/api/users')
        .then(response => {
            this.users = response.data;
          });
    },
  }
</script>