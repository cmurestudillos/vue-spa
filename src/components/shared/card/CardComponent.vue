<template>
  <div class="container mt-4">
    <div class="row row-cols-1 row-cols-sm-2 row-cols-md-3 row-cols-lg-4">
      <div class="col p-1" v-for="heroe in heroes" :key="heroe.nombre">
        <div class="card h-100 shadow animated fadeIn slow m-2">
          <img :src="heroe.img" :alt="heroe.nombre" class="card-img-top img-fluid" />
          <div class="card-body">
            <h5 class="card-title">{{ heroe.nombre }}</h5>
            <p class="card-text">{{ heroe.bio }}</p>
            <small class="text-muted"><strong>Año:</strong> {{ heroe.aparicion }}</small>
          </div>
          <div class="card-footer">
            <router-link :to="'/heroe/' + heroe.nombre" class="btn btn-4 mt-2">Ver mas...</router-link>
          </div>
        </div>
      </div>
    </div>
  </div> 
</template>

<script>
// Datos a cargar
import customData from '../../../data/heroes.json';
export default {
    name: 'CardComponent',
    components: {
    },
    data(){
        return {
            heroes: customData
        }
    }
}
</script>