<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div v-for="user in users" :key="user.id">
      <p>{{ user.id }}: {{ user.name }}</p>
    </div>
  </div>
</template>

<script>
const API_URL = "http://localhost:8000/users";

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data: () => ({
    users: []
  }),

  mounted() {
    fetch(API_URL)
      .then(response => response.json())
      .then(users => {
        this.users = users;
      });
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
