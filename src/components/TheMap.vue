<template>
<ol-map
  :loadTilesWhileAnimating="true"
  :loadTilesWhileInteracting="true"
  style="height: 400px"
>
  <ol-view
    ref="view"
    :center="center"
    :rotation="rotation"
    :zoom="zoom"
    :projection="projection"
  />

  <ol-tile-layer>
    <ol-source-osm />
  </ol-tile-layer>
</ol-map>
</template>

<script setup lang="ts">
import { ref, inject } from 'vue';

const center = ref([40, 40]);
const projection = ref('EPSG:4326');
const zoom = ref(3);
const rotation = ref(0);

const format = inject('ol-format');
const geoJson = new format.GeoJSON();
</script>
