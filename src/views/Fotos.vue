<template>
    <div id="FotosView">
        <h1>Álbum</h1>
        <div class="grid_foto">
            <div v-for="i in 6" :key="i">
                    <h3>Foto {{i}}</h3>
                    <a @click="redirect(i)">
                    <img :src="srcImage(i)" alt="">
                    </a>
            </div>
        </div>
    </div>
</template>

<script>
    export default{
        name: 'FotosView',
        data: function(){
            return{

            }
        },
        methods: {
            srcImage(id){
                return ` https://picsum.photos/200/300?grayscale/${id}`
            },
            redirect(id){
                this.$router.push(`/fotos/${id}`)
            }


        }
    }

</script>

<style scoped>

        .grid_foto{
            /*aqui hace que la vista de las fotos se separe en tres columnas (1fr 1fr 1fr)*/
            display:grid;
            grid-template-columns: 1fr 1fr 1fr;
        }


</style>