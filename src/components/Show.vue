<template>
  <div class="show">
    <h3>{{ show.name }} <span v-if="show.rating.average">({{ show.rating.average }})</span></h3>
    <img class="show-image" v-if="show.image" :src="show.image.original" :alt="show.name">
  </div>
</template>



<script>
export default {
  name: 'show',
  props: [
    'show'
  ],
  data(){
    return {

    }
  }
}
</script>





<style scoped>
.show {
  flex: 0 1 30%;
  display: flex;
  flex-direction: column;
}

.show-image{
  max-width: 40%;
  margin: auto;
}

</style>
