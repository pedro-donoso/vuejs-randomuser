<template>
    <div id="app">
      <div v-for="user in users" v-bind:key="user.id">
        <h1>{{ user.name }}</h1> 
        <p>{{ user.email }}</p>
        <p>{{ user.phone }}</p> 
         <p>{{ user.phone }}</p> 
      </div>
      <button @click="fetchUsers">Cargar datos</button>
    </div>
</template>

<script>

const users = "https://jsonplaceholder.typicode.com/users/"


export default {
  name: 'app',
  data () {
    return {
      users: []
    }
  },
  methods: {
    fetchUsers: function () {
      let number = users
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

</style>
