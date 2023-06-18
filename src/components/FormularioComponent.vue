
<template>
    <div id="formularioComponent">
        <h1>Formulario Factura</h1>
        <form action="">
            <label for="txtNombre">Nombre:</label>
            <input type="text" id="txtNombre" v-model="losDatos.elNombre"><br>
            <label for="txtApellido">Apellido:</label>
            <input type="text" id="txtApellido" v-model="losDatos.elApellido"><br>
            <input type="submit" v-on:click.prevent="enviarAlPadre" value="enviar">
        </form>
    </div>
</template>

<script>
    export default{
        name: 'FormularioComponent',
        data: function(){
            return{
                losDatos:{
                    elNombre: '',
                    elApellido: ''   
                }
                
            }
        },
        methods:{
            enviarAlPadre: function(){
                this.$emit('datosForm', this.losDatos);
            }
        }
    }

</script>

<style>
 
</style>