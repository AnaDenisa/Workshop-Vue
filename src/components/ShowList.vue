<template>
  <div id = "showlist">
    <div class = "show-results">
      <show v-for="(item, index) in shows" :show="item.show" :key="index"></show>
    </div>
  </div>
</template>


<script>
import show from '@/components/Show'

export default {
  name: 'showlist',
  components: {
    show
  },
  data(){
    return {
      api: 'http://api.tvmaze.com/search/shows',
      query: '',
      shows: []
    }
  },
  created(){
  this.$root.$on('search-show', (data) => {
    this.query = data;
    this.searchQuery(this.query);
    })
  },
  methods: {
    async searchQuery(q){
      this.shows = (await this.$http.get(`${this.api}?q=${q}`)).data;
      console.log(this.shows);
    }
  }
}
</script>


<style scoped>
  .show-results{
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    margin-bottom: 2rem;
  }
</style>
