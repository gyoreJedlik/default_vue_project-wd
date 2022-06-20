+<template>
  <div class="container my-5">
      <div class="row mb-5">
          <select-season :seasons="seasons" @onSelectedSeason="onSelectedSeason"/>
      </div>
      <div class="row">
          <film-card/>
      </div>
  </div>
</template>

<script>
import DataService from '@/services/dataservice'

import FilmCard from '@/components/FilmCard.vue'
import SelectSeason from '@/components/SelectSeason.vue'


export default {
    name:"walking-dead",
    components:{FilmCard, SelectSeason},
    data(){
        return{
            seasonList:[],
            seasons:[],
        }
    },
    created(){
        DataService.getAllFilms()
            .then(result =>{
                this.seasons = [...new Set(result.map(x => x.seasons))]  // ... egymas után fűzi a dolgokat 
                this.seasonList=result})
    },
    methods:{
        oneSelectSeason(event){
            console.log(event.target.value)
        }
    }

}
</script>

<style>

</style>