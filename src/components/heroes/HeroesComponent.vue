<template>
    <div>
        <h1 class="text-white">Heroes <small>Marvel y DC</small></h1>
        <hr class="text-white">
        <CardComponent />
    </div>
</template>

<script>
// Componentes
import CardComponent from '../shared/card/CardComponent.vue';

export default {
    name: 'HeroesComponent',
    components: {
        CardComponent
    } 
}
</script>