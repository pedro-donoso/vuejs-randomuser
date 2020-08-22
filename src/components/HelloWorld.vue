<template>
    <div id="app">
      <div v-for="user in users" v-bind:key="user.id">
        <h1>{{ user.name }}</h1> 
        <p>{{ user.email }}</p>
        <p>{{ user.phone }}</p> 
      </div>
      <button @click="fetchUsers">Cargar datos</button>
    </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      users: []
    }
  },
  methods: {
    fetchUsers: function () {
      let number = Math.round(Math.random()*10); //Número aleatorio
      if(number == 0) number + 1;
      const baseURI = `https://jsonplaceholder.typicode.com/users/${ number }` //Api de usuarios
      this.$http.get(baseURI)
      .then((result) => {
        this.users = result
      })
    }
  }
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
