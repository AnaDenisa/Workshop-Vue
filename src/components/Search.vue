<template>
  <div class = "search">
    <input class = "search-input" v-on:change="searchShow" type = "search" placeholder = "Search for a show">
    <showlist></showlist>
  </div>
</template>



<script>
import showlist from '@/components/ShowList'

export default {
  name: 'search',
  components: {
    showlist
  },
  data(){
    return {

    }
  },
  methods: {
    searchShow(e){
      this.$root.$emit('search-show', e.target.value)
      console.log(e.target.value);
    }
  }

}
</script>



<style>
</style>
