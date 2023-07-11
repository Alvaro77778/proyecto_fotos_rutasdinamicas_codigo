<template>
    <div id="FotoVue">
        <router-link to="/fotos" class="textVolver">Volver</router-link>
        <h1>Componente Foto</h1>
        <h2>Foto: {{ id }}</h2>
        <img v-bind:src="rutaImagen" alt="">
        

    </div>

</template>

<script>
    export default{
        name: 'FotoVue',
        data: function(){
            return{
                rutaImagen: ''
            }
        },
        methods:{
            
        },
        computed: {
            id: function(){
                return this.$route.params.id;
            }
        },
            //hook
        created(){
                this.rutaImagen = `https://picsum.photos/200/300?grayscale/${this.id}`
        }
    }

</script>

<style scoped>
    #FotoVue{
        background-color: darkcyan;
        color: white;
    }
    .textVolver{
        color: white;
    }


</style>