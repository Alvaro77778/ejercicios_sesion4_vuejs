<template>
    <div id="datosComponent">
        <h1>Datos Factura</h1>
        <p>Factura para : {{ unNombre }} {{ unApellido }}</p>
        <p>Fecha actual: {{ fechaActual }}</p>
        <button v-on:click="generarFecha">generarFecha</button>
    
    </div>
</template>

<script>
    export default{
        name:'datosComponent',
        props: ['unNombre','unApellido'],
        data: function(){
            return{
                fechaActual: '',
            }
        },
        methods:{
            generarFecha: function(){
                const tiempoTranscurrido = Date.now();
                const hoy = new Date(tiempoTranscurrido);
                
                this.fechaActual = hoy.toDateString(); // "Sun Jun 16 2023"
            }
        }
    }
</script>

<style>
    
</style>