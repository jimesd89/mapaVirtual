<template>
    <div ref="mapContainer" class="map-container"></div>
</template>
<script setup lang="ts">
import {onMounted, ref} from 'vue';
import mapboxgl from 'mapbox-gl'; // or "const mapboxgl = require('mapbox-gl');"
import 'mapbox-gl/dist/mapbox-gl.css';
// TO MAKE THE MAP APPEAR YOU MUST
// ADD YOUR ACCESS TOKEN FROM
// https://account.mapbox.com
mapboxgl.accessToken = 'pk.eyJ1IjoiamltZW5hbWFwOTkiLCJhIjoiY2xkOWg1MHF1MDcwcjNvczl3MWlmYWo0YSJ9.4JljQunKYrxQkJZF8XjAHA';
const mapContainer = ref<HTMLElement>()

onMounted(() =>{

    //ref<HTMLElement>()
   const map = new mapboxgl.Map({
	container: mapContainer.value!, // container ID !confirma que siempre tiene un valor
	style: 'mapbox://styles/mapbox/satellite-v9', // style URL puedo cambiar de streets-v12 a /satelite-v9
	center: [-74.5, 40], // starting position [lng, lat]
	zoom: 2, // starting zoom
    projection: 'globe'
}as any);
map.on('style.load', () => {
    map.setFog({
         color: 'rgb(186, 210, 235)', // Lower atmosphere
    'high-color': 'rgb(36, 92, 223)', // Upper atmosphere
    'horizon-blend': 0.02, // Atmosphere thickness (default 0.2 at low zooms)
    'space-color': 'rgb(11, 11, 25)', // Background color
    'star-intensity': 0.6 // Background star brightness (default 0.35 at low zoooms
    });
})
})

</script>
<style scoped>
.map-container{
    width: 100vw;
    height: 100vh;
}
</style>