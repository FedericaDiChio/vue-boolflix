<template>
  <header class="d-flex align-items-center justify-content-between bg-dark">
      <h1 class="ms-4 text-danger">Boolflix</h1>
      <Search  @doSearch="search" />
  </header>
</template>

<script>
import axios from "axios"
import Search from "@/components/Search.vue";
export default {
    components: { Search },
    name: "Header",
    data(){
      return {
        searched: [],
        api: {
          key: "7eda76818c444074e8b197168aca5a02",
          uri: "https://api.themoviedb.org/3"
        }
      }
    },
    methods: {
      search(query){
        axios.get(`${this.api.uri}/search/movie?api_key=${this.api.key}&query=${query}`).then((res) => { 
          this.searched = res.data.results;
        }) 
      }  
  },
    created(){},
}
</script>

<style>

</style>