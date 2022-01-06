<template>
  <h2>{{tituloComputado}}</h2>
  <p> {{contador}} <sup>2</sup> = {{contadorAlCuadrado}} </p>
  <div>
      <button @click="suma">+1</button> <button @click="resta">-1</button>
  </div>
</template>

<script>
export default {
    props:{
        titulo: String,
        inicio: {
            type: Number,
            default: 12,
            validator(value){
                return value > 0
            }
        }

    },


    data(){
        return{
            contador: this.inicio
        }
    },
    methods: {
        alCuadrado(){
            return this.contador * this.contador
        },

        suma(){
            this.contador ++
        },
         resta(){
            this.contador-- 
        }
    },
    computed: {
        contadorAlCuadrado(){
            return this.contador * this.contador
        },
        tituloComputado(titulo){
            // return this.titulo? this.titulo : 'No hay titulo'
            // lo de arriba puede simplificarse con:
            return this.titulo || 'No hay titulo'
        }
    }

}
</script>

<style>

</style>