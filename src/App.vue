<template>
 <div>
    <h1>Queens</h1>
    
    <queen-filter-form :queens="queens" />
    <queen-detail :queen="selectedQueen"/>
  </div>
</template>

<script>
import QueenFilterForm from './components/QueenFilterForm.vue'
import QueenDetail from './components/QueenDetail.vue'
import {eventBus} from './main.js';


export default {
  data(){
    return {
      queens: [],
      selectedQueen: null
    }
},
components: {
    "queen-filter-form": QueenFilterForm,
    "queen-detail": QueenDetail
},
mounted(){
    fetch('http://www.nokeynoshade.party/api/queens/all/')
    .then(res => res.json())
    .then(data => this.queens = data)

    eventBus.$on('queen-selected', (queen) => {
      this.selectedQueen = queen
    })
  }
}
</script>

<style>

body {
  width: 100%;
  height:100%;
}

body {
    background: linear-gradient(-45deg, #ee7752, #e73c7e, #f020c3, #ff0554);
    background-size: 10000% 10000%;
    animation: gradient 10s ease infinite;
}

@keyframes gradient {
    0% {
        background-position: 0% 50%;
    }
    50% {
        background-position: 100% 50%;
    }
    100% {
        background-position: 0% 50%;
    }
}

.center
{
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  width: 100%;
}

h1 {
  text-align: center;
  font-size: 100px;
  text-transform: uppercase;
  color: transparent;
  background-image: linear-gradient(to right, #fcb606d6, #ffff00);
  -webkit-background-clip: text;
  animation: animate 5s linear infinite;
  background-size: 1000%;
}

@keyframes animate {
    0% {
        background-position: 0% 50%;
    }
    50% {
        background-position: 100% 50%;
    }
    100% {
        background-position: 0% 50%;
    }
}
</style>


