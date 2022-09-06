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

    <div id="container">
      <!-- Click para cambiar mostrar mensaje y cambiar variable a true-->
      <div class="row1-container">
        <div class="box box-down cyan">
          <button v-on:click="greet">Clickame</button>
          <h2 v-if="first">Hello! Gracias por clickar!</h2>
          <h2 v-else>Va, haz click arriba</h2>
        </div>

        <!-- Click para cambiar mostrar mensaje y cambiar variable a true-->
        <div class="box red">
          <button v-on:click="showClick"><div>Clickeame API</div></button>
          <div v-if="show" id="API">
            Aqui el tochaco de la API:{{ projects }}
          </div>
          <h2 v-else>Click para la API</h2>
        </div>
      </div>

      <!-- Click para cambiar mostrar mensaje y cambiar variable a true-->
      <div class="box box-down blue">
        <button v-on:click="showLuz"><div>Apaga la luz</div></button>
        <div v-if="luz">Luz apagada</div>
        <h2 v-else>Apaga la luz</h2>
      </div>

      <div class="row2-container">
        <div class="box orange">
          <button @click="submitForm">Enviar</button>
          <h2>Test on click</h2>
        </div>
      </div>

      <div class="box">
        <form>
          <input type="text" placeholder="Tu nombre" />
        </form>
      </div>

      <article id="forEachBox">
        <h1>Esto es un for-each de la api:</h1>
        <div v-for="item in projects" :key="item.uuid" id="proyectos">
          <p>Proyecto nº{{ item.uuid }} trata de {{ item.name }}</p>
        </div>
      </article>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    placeholder: String,
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
      color: "white",
      name: null,
      email: null,
      aboutMe: null,
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
      this.color = "black";
      alert("Apagando luz");
    },

    superFunction() {
      return (this.superString = "Hola que tal");
    },

    submitForm() {
      alert("Pa que clickas");
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
#oscuro {
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
  width: 100px;
  align-content: center;
  justify-content: center;
}

#API {
  display: flex;
  padding: 20px;
  font-size: 10px;
}

#proyectos {
  display: flex;
  align-content: center;
  align-items: center;
  background-color: #04aa6d;
  font-weight: 400;
  margin: 5px;
  border-radius: 50px;
  justify-content: center;
}

/* Hola */

body {
  font-size: 15px;
  font-family: "Poppins", sans-serif;
  background-color: hsl(0, 0%, 98%);
}

h2:first-of-type {
  font-weight: 200;
  color: hsl(234, 12%, 34%);
}

h2:last-of-type {
  color: hsl(234, 12%, 34%);
}

@media (max-width: 400px) {
  h2 {
    font-size: 1.5rem;
  }
}

.box p {
  color: hsl(229, 6%, 66%);
}

.box {
  border-radius: 5px;
  box-shadow: 0px 30px 40px -20px hsl(229, 6%, 66%);
  padding: 30px;
  margin: 20px;
  border-radius: 20px;
  width: 200px;
  align-content: center;
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  align-items: center;
}

img {
  float: right;
}

@media (max-width: 450px) {
  .box {
    height: 200px;
  }
}

@media (max-width: 950px) and (min-width: 450px) {
  .box {
    text-align: center;
    height: 180px;
  }
}

.cyan {
  border-top: 3px solid;
  color: cyan;
}
.red {
  border-top: 3px solid;
  color: red;
}
.blue {
  border-top: 3px solid;
  color: blue;
}
.orange {
  border-top: 3px solid;
  color: orange;
}

h2 {
  color: darkblue;
  font-weight: 300;
}

.box form {
  display: flex;
  align-content: center;
  align-items: center;
  justify-content: center;
}

#container {
  display: flex;
  align-content: center;
  flex-direction: column;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
}
</style>
