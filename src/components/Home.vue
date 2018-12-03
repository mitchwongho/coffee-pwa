<!-- Template -->
<template>
  <div class="mdl-grid">
    <div id="pwa-geo-search" class="mdl-cell mdl-cell--1-col">
      <!-- Searchbar -->
    </div>
    <div id="pwd-geo-poi" class="mdl-cell mdl-cell--6-col mdl-cell--4-col-phone">
      <!-- list of POI -->
      <div v-for="poi in this.pois" class="image-card">
        <img :src="poi.imageUrl" />
      </div>
    </div>
  </div>
    
</template>
<!-- Scripting-->
<script>
  import data from '../data'
  export default {
    methods: {
      displayDetails (id) {
        // todo
      },
      geolocation () {
        navigator.geolocation.getCurrentPosition(this.onPositionFound, this.onGeoError)
      },
      onPositionFound (position) {
        console.log('Position found:{0},{1}', position.coords.latitude, position.coords.longitude)
      },
      onGeoError (error) {
        console.log('Oops. Error getting Geolocation: {0}', error)
      }
    },
    data () {
      return {
        'pois': data.pois
      }
    },
    beforeMount () {
      this.geolocation()
    }
  }
</script>
<!-- Style -->
<style scoped>
  .image-card {
    position: relative;
    margin-bottom: 8px;
  }
  .image-card__picture > img {
    width: 100%;
  }
</style>

