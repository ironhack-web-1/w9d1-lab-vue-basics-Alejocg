<template>
  <div class="hello">
    <h1>{{ msg }}</h1>

    <p>
      Aquí voy a hacer mis experimentos con VUE.js.
    </p>
    <div> Esto es un string: {{hola}} y una suma calculada en otro componente: {{math}}</div>
    <div> Esto es una string de una funcion: </div>
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
      hola: 'hola soy un string dentro del componente',
      math: 2+2,
      property: "blank",

  
    }
  }
};


</script>

<style scoped>

div {
  display: flex;
  width: 100%;
  align-items: center;
  flex-direction: column;
  
}

</style>
