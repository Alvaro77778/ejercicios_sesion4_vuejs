<template>
        <div class="hello">
            <h1>{{ msg }}</h1>
            <div id="divContador">
                <p id="contador"> Contador: {{ contador }}</p>
            </div>
            <button v-on:click="contador+=1" >Presioname</button>

           
            <div id="datosEvento">
                <p id="pDatoEvento">Dato evento: {{  datosEvento }}</p>
            </div>
            <div id="divBtnVerDatos"> 
                <button v-on:click="verEvento">Ver datos del evento click</button>
            </div>
        </div>
  </template>
  
  <script>
        export default {
            name: 'HelloWorld',
            props: {
            msg: String,
            },
            data: function(){
                return{
                    contador: 0,
                    datosEvento: '',
                }
            },
            methods:{
                verEvento: function(event){
                    console.log(event);
                    this.datosEvento = event.target.tagName;
                }
            },
        }
  </script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped>
        h3 {
            margin: 40px 0 0;
        }
        ul {
            list-style-type: none;
            padding: 0;
        }
        li {
            display: inline-block;
            margin: 0 10px;
        }
        a {
            color: #42b983;
        }
        
        .hello{
            background-color: darkgoldenrod;
        }

        #contador{
            font-weight: bold;
        }

        #pDatoEvento{
            font-weight: bold;
        }
        #datosEvento{
            display: flex;
            justify-content: center;
        }

        #divContador{
            display: flex;
            
            justify-content: center;
            
            
        }

        #divBtnVerDatos{
            display: flex;
            justify-content: center;
            padding-bottom: 10px;
        }
  </style>