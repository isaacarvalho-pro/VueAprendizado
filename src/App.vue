<template>
  <TheHeader v-show="showHeader">
  </TheHeader>


  <div>
    <h1 :class="classVar">curso vue.js 3</h1>


    <p :class="pClass">

      Lorem ipsum dolor sit amet, consectetur adipiscing elit. Cras sit amet posuere ligula. Nulla nec lacinia lacus, eu vulputate mi. Cras nec vehicula lacus. Nunc non mollis nulla. Praesent semper sed elit eu faucibus. Nulla egestas ante ac elit porta finibus. Aenean mattis nisi justo, eget facilisis massa hendrerit ut. Integer euismod sem mauris, vestibulum vestibulum purus luctus eu.

      Suspendisse dignissim auctor enim, sed accumsan felis vehicula ut. Morbi lacinia tellus dolor, non vulputate mauris malesuada ut. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Nam vitae pretium purus. Quisque vel turpis quam. Mauris metus metus, elementum et vehicula ut, accumsan quis neque. Cras venenatis metus vitae pellentesque facilisis. Morbi vitae placerat nunc. Ut nec libero mi. Curabitur ac sagittis nulla. Phasellus pellentesque condimentum volutpat. Morbi mattis, diam at faucibus hendrerit, quam purus interdum odio, ut auctor erat ligula vitae erat. Proin efficitur nisi a nulla dignissim, eu vulputate ex cursus.
    </p>


    <p :style="styleVar">
      Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas orci turpis, cursus in elit eu, fringilla scelerisque tortor. Suspendisse potenti. In sodales hendrerit ex, sed ornare dui mattis at. Donec sollicitudin tincidunt rhoncus. Nunc vitae placerat est. Maecenas ipsum libero, ultricies vitae elit quis, rhoncus mattis urna. Integer interdum ornare elit, a tempus augue tincidunt ut. Fusce sodales et dolor ac consectetur. Duis vel diam tempor, aliquam dolor nec, rhoncus ipsum. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Etiam mollis rutrum tristique. 
    </p>
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
      styleVar: {'color': 'white', backgroundColor: 'black'},
      pClass: 'paragrafo',
      classVar: {'titulo': true},
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

.paragrafo{
  color: lightseagreen


}
</style>
