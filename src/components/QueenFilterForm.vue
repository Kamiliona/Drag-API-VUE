<template>
   <form v-on:submit.prevent>
    <input type="text" v-model="search" placeholder="who is your Queen?" v-on:keyup="searchForQueen">
    <select v-on:change="handleSelect" v-model="selectedQueen">
      <option disabled value="">Long live the ...</option>
      <option v-for="queen in queens" :value="queen" :key="queen.id">{{queen.name}}</option>
    </select>
  </form>
</template>

<script>
import { eventBus } from '../main.js'

export default {
  name: "queen-filter-form",
  data(){
    return {
      "search": "",
      "selectedQueen": {},
    }
  },
  props: ["queens"],
  methods: {
    searchForQueen(){
      let foundQueen = this.queens.find((queen) => {
        return queen.name.toLowerCase().indexOf(this.search.toLowerCase()) > -1
      })
      this.selectedQueen = foundQueen

      eventBus.$emit('queen-selected', this.selectedQueen)
    },
    handleSelect(){
      this.search = ""
      eventBus.$emit('queen-selected', this.selectedQueen)
    }
  }
}
</script>

<style>

form{
  text-align: center;
  margin: 40px 0;
 
}

select, input[type="text"]{
  font-size: 18px;
  border-radius: 15px;
  margin: 10px;
   height:50px;
   width: 500px;
    font-size:14pt;
  
}

select {
  margin-left: 20px;
}
</style>