<template>
  <div class = "test">
    <button v-on:click="inc">{{counter}}</button>
    <ul>
      <li v-for="item in users"> {{item.name}} </li>
    </ul>
  </div>

</template>


<script>
export default {
  // for (item in list)
  name: 'test',
  data(){
    return {
      api: 'https://jsonplaceholder.typicode.com/users',
      counter: 0,
      list: [
        {
          name: 'Irina',
          boolean: true
        },
        {
          name: 'Ana',
          boolean: true
        },
        {
          name: 'Cristi',
          boolean: false
        }
      ],
      users: []
    }
  },
  methods: {
    inc: function(){
      this.counter = this.counter + 1;
    }
  },
  created() {
    this.$http.get(this.api).then(function (response){
      this.users = response.data;
      console.log(this.users);
    })
  }
}


</script>


<style scoped>

</style>
