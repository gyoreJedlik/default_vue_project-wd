<template>
  <div class="card-group col-12 col-md-3 mb-2" v-for="item in seasonList" :key="item.id">
    <div class="card">
        <img v-if="item.image" :src="item.image.medium" class="card-img-top" alt="...">
        <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text" v-html="item.summary"></p>  <!--formázott szöveg kiírása-->
        <div class="card-footer d-flex justify-content-center">
            <a :href="item.url" target="_blank" class="btn btn-primary ">Go to webpage</a>    <!-- : változót csinál belőle-->
        </div>
        <p class="card-text"><small class="text-muted">Last updated 3 mins ago</small></p>
        </div>
    </div>
</div>
</template>

<script>
export default {
    name:"film-card",
    props:['seasonList']
}
</script>

<style>

</style>