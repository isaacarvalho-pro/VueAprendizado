<template>
  <TheHeader v-show="showHeader">
  </TheHeader>


  <div>
    <h1 :class="{'titulo': true, 'titulo-home': isHome}">curso vue.js 3</h1>
  </div>



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

    <img
      v-if="obj.imgSrc" 
      v-bind:src="obj.imgSrc" 
      
      :alt="imgAlt">
    {{index}}-{{ obj.title }}
  </div>
<!--podemos usar : em vez de v-bind -->


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
      isHome: true,
      classVar: 'titulo',
      imgAlt: 'Imagem teste',
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
            "completed": false,
            "imgSrc": "https://placehold.co/40",
          },
          {
            "userId": 1,
            "id": 2,
            "title": "quis ut nam facilis et officia qui",
            "completed": false,
            "imgSrc": "https://placehold.co/40",
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


.titulo{
  color: blue;
}

.titulo-home{
  color: red;
  font-size: 100px;
}
</style>
