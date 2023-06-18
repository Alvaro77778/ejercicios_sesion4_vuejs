<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <eventModifier/>
    <h2>CONTENEDOR</h2>

    <p id="nombrePadre">Nombre: {{ objetoRecibido.nombreRecibido }}</p>
    <p id="apllPadre">Apellido: {{ objetoRecibido.apellidoRecibido }}</p>
    
    <h2>PADRE</h2>

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
  background: rgb(34,193,195);
  background: linear-gradient(0deg, rgba(34,193,195,1) 0%, rgba(253,187,45,1) 100%);
}

#contenedorPadre{
  display: flex;
  justify-content: center;
}

#contenedorFormulario{
  height: 200px;
  width: 49%;
  background-color: aqua;
  display: inline-block;
}

#contenedorDatos{
  height: 200px;
  width: 49%;
  background-color: greenyellow;
  display: inline-block;
}

#nombrePadre{
  color: red;
  font-weight: bold;
}

#apllPadre{
  color:blue;
  font-weight: bold;
}

</style>
