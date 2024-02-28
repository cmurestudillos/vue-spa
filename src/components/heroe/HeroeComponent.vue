<template>
    <div class="bg-white shadow-lg p-3 mb-5 bg-white rounded">
        <h1 class="animated fadeIn slow">{{heroe.nombre}} <small>( {{heroe.aparicion}} )</small></h1>
        <hr>
        <div class="row animated fadeIn slow">
            <div class="col-md-4">
                <img :src="`../${heroe.img}`" :title="heroe.nombre" class="img-fluid shadow" :alt="heroe.nombre" />
                <br><br>
                <button @click="volver()" type="button" class="btn btn-4 btn-block"><i>Volver</i></button>
            </div>
            <div class="col-md-8">
                <h3>{{heroe.nombre}}</h3>
                <hr>
                <p>{{heroe.bio}}</p>
                <div>
                    <img v-if="heroe.casa == 'DC'" src="../../../public/assets/img/dc.svg" :title="heroe.casa" class="img-fluid" width="150" height="150" :alt="heroe.casa" />
                    <img v-if="heroe.casa == 'Marvel'" src="../../../public/assets/img/marvel.svg" :title="heroe.casa" class="img-fluid" width="150" height="150" :alt="heroe.casa" />
                </div>
            </div>
        </div>
    </div>
</template>

<script>
// Datos a cargar
import customData from '../../data/heroes.json';

export default {
    name: 'HeroeComponent',
    mounted(){
        this.getHeroe();
        console.log(this.heroe);
    },  
    data(){
        return {
            heroe: []
        }
    },     
    methods: {
        getHeroe(){
            this.heroeNombre = this.$route.params.nombre; 
            for (let index = 0; index < customData.length; index++) {
                if (this.heroeNombre === customData[index].nombre){
                    this.heroe = customData[index];
                }
            }
        },
        volver(){
            this.$router.push('/heroes');
        }        
    }       
}
</script>