<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <eventModifier/>

    <p>Nombre: {{ objetoRecibido.nombreRecibido }}</p>
    <p>Apellido: {{ objetoRecibido.apellidoRecibido }}</p>
    <hr>

    <div id="contenedorPadre">
      <div id="contenedorFormulario">
        <formularioComponent
        v-on:datosForm="recibirDatosForm"
        />
      </div>
      <div id="contenedorDatos">
        <datosComponent
          v-bind:unNombre= "objetoRecibido.nombreRecibido"
          v-bind:unApellido = "objetoRecibido.apellidoRecibido"
        />
      </div>
    </div>
    
  </div>
</template>

<script>
import eventModifier from './components/EventModifier.vue';
import formularioComponent from './components/FormularioComponent.vue';
import datosComponent from './components/DatosComponent.vue';
export default {
  name: 'App', 
  components: {
    eventModifier,
    formularioComponent,
    datosComponent
  },
  data: function(){
    return{
      objetoRecibido:{
        nombreRecibido: '',
        apellidoRecibido: '',
      }
    }
  },
  methods:{
    recibirDatosForm: function(objetoDatosDelHijo){
      this.objetoRecibido.nombreRecibido = objetoDatosDelHijo.elNombre;
      this.objetoRecibido.apellidoRecibido = objetoDatosDelHijo.elApellido;
    }
  }
}
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

#contenedorPadre{
  
}

#contenedorFormulario{
  width: 49%;
  background-color: aqua;
  display: inline-block;
}

#contenedorDatos{
  width: 49%;
  background-color: greenyellow;
  display: inline-block;
}
</style>
