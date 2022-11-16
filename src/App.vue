<template>
  <div class = left>
  <AtomicClock api = "https://incredibly-mythical-possum-cell-dev.wayscript.cloud/london" title='London'/>

  </div>
  <div class = middle>
  <AtomicClock api = "https://incredibly-mythical-possum-cell-dev.wayscript.cloud/america" title='Toronto'/>
 
  </div>
  <div class = right>

  </div>
 
</template>

<script>

import AtomicClock from "./components/AtomicClock.vue"
export default {
  name: 'App',
  components: {
    AtomicClock,

  },

}
</script>

<style>
.left{
  position:absolute; top:1.875rem;
}
.middle{
  position:absolute; left:31.25rem; top:1.875rem;
}
.right{
  position:absolute; left:62.50rem; top:1.875rem;;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  
}
body {
  background-color: rgb(159, 150, 184);
}
</style>
