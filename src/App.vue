<template>
  <div id="app" class="container">
    <h6 class="pasos">Obtén el Nombre, Correo y Telefono de Usuario Random:</h6>
    <img alt="Vue logo" src="./assets/logo.png">
<Usuarios />
  </div>
</template>

<script>
import Usuarios from './components/Usuarios'

export default {
  name: 'app',
  components: {
    Usuarios
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;

}

body{
  background: rgba(230,235,62,10);
}

.pasos{
  background: orange;
}

</style>
