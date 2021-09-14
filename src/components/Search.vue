<template>
  <div>
      <input type="text"
      v-model.trim="userInput">
      <button @click="$emit('doSearch', userInput)">Cerca</button>
  </div>
</template>

<script>
export default {
    name: "Search",
    data(){
      return {
        userInput: " ",
      }
    },
    methods: {
    },
    created(){},
}
</script>

<style>

</style>