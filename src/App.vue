<template>
  <TheHeader v-show="showHeader">
  </TheHeader>

  <div v-show="showName">
    Nome: {{
      firstName
    }}

    <br>

    Sobrenome: {{
      lastName
    }}
  </div>


  <div v-if="accessLevel === 'admin'">
    Admin
  </div>
  <div v-else-if="accessLevel === 'marketing'">
    Funcionario Marketing
  </div>
  <div v-else>
    Usuario
  </div>

  <br>
              <!--obj é uma variavel local-->
  <div v-for="(obj, index) in todos" v-bind:key="obj.id">

    {{index}}-{{ obj.title }}
  </div>


</template>

<script>
import TheHeader from './components/TheHeader.vue'

export default {
  name: 'App',
  components: {
    TheHeader
  },
  data() {
    return {
      showHeader: true,
      firstName: 'Isaac',
      lastName: 'Carvalho da Mota',
      showName: true,
      accessLevel: 'admin',
      todos:
        [
          {
            "userId": 1,
            "id": 1,
            "title": "delectus aut autem",
            "completed": false
          },
          {
            "userId": 1,
            "id": 2,
            "title": "quis ut nam facilis et officia qui",
            "completed": false
          },
          {
            "userId": 1,
            "id": 3,
            "title": "fugiat veniam minus",
            "completed": false
          },
          {
            "userId": 1,
            "id": 4,
            "title": "et porro tempora",
            "completed": true
          },
          {
            "userId": 1,
            "id": 5,
            "title": "laboriosam mollitia et enim quasi adipisci quia provident illum",
            "completed": false
          }
        ]
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
