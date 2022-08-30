<template>
  <div id="oscuro">
    <h1>{{ msg }}</h1>

    <p>Aquí voy a hacer mis experimentos con VUE.js.</p>
    <div>
      Esto es un string: {{ hola }} y una suma calculada en otro componente:
      {{ math }}
    </div>
    <div>Esto es una string de una funcion: {{ superFunction() }}</div>
    <p></p>
    <!-- Click para cambiar mostrar mensaje y cambiar variable a true-->
    <button v-on:click="greet">Clickame</button>
    <h1 v-if="first">Hello! Gracias por clickar!</h1>
    <h1 v-else>Va, haz click arriba</h1>

    <!-- Click para cambiar mostrar mensaje y cambiar variable a true-->
    <button v-on:click="showClick"><div>Clickeame API</div></button>
    <div v-if="show" id="API"> Aqui el tochaco de la API:{{ projects }}</div>
    <h1 v-else>Click para la API</h1>
    
    <!-- Click para cambiar mostrar mensaje y cambiar variable a true-->
    <button v-on:click="showLuz"><div>Apaga la luz</div></button>
    <div v-if="luz"> Luz apagada </div>
    <h1 v-else>Apaga la luz</h1>
    
    <article id="forEachBox"> 
    <h1>Esto es un for-each de la api:</h1>
    <div v-for="item in projects" :key="item.uuid" id="proyectos">
    <p> Proyecto nº{{item.uuid}} trata de {{item.name}}</p> 
    </div>
   </article>


  </div>

  



</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },

  data() {
    return {
      palabra: "hola",
      projects: [],
      hola: "hola soy un string dentro del componente",
      math: 2 + 2,
      first: false,
      show: false,
      luz: false,
      color: 'white',
      post1: [
        { title: "El vue" },
        { description: "Codigo guay" },
        { content: "Contenido" },
      ],
      post2: [
        { title: "El vue 2" },
        { description: "Codigo guay 2" },
        { content: "Contenido 2" },
      ],
      post3: [
        { title: "El vue 3" },
        { description: "Codigo guay 3" },
        { content: "Contenido 3" },
      ],
    };
  },

  methods: {
    greet: function (event) {
      // `this` inside methods point to the Vue instance
      this.first = true;
      alert("Ahora te aparece el h1");
    },

    showClick: function (event) {
      this.show = true;
      alert("Ahora te aparece lo de la API");
    },

    showLuz: function (event) {
      this.luz = true;
      this.color = 'black';
      alert("Apagando luz");
      
    },

    superFunction() {
      return (this.superString = "Hola que tal");
    },
  },

  beforeMount() {
    fetch(
      "https://raw.githubusercontent.com/ironhack-jc/mid-term-api/main/projects"
    ).then((res) => {
      res.json().then((projects) => {
        this.projects = projects;
      });
    });
  },
};
</script>

<style scoped>


#oscuro{
  background-color: v-bind(color);
}

button {
  background-color: #04aa6d;
  border: none;
  color: white;
  padding: 20px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  cursor: pointer;
}

div {
  display: flex;
  width: 100%;
  align-items: center;
  flex-direction: column;
}

#API {
  display: flex;
  padding: 20px;
  font-size: 10px;
}

#proyectos {
  display:flex;
  align-content: center;
  align-items: center;
  background-color: #04aa6d;
  font-weight: 400;
  margin:5px;
  border-radius: 50px;
}
</style>
