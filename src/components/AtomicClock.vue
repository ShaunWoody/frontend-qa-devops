<template>

<div class = "clock-border">
  
  <h1 class = "title">{{title}}</h1>

  <p class = "time">{{data}}</p>

  
  </div>
</template>

<script>
export default {
  name: 'AtomicClock',
  props: {
    api: String,
    title: String

  },
  data() {
    return {
      status: true,
      data: [],
      time: '',
      timer:null,
      test:''
    };
  },
  setup(){

  },
  methods: {
    async reNew() {
     // try{ 
      
      const response = await fetch(this.api,
      {
        method: 'get',
        
        
      });
      
      this.data = await response.json();
      this.time = this.data.time;

      setTimeout(this.reNew,250)
    //}
    //catch (error) {
    //  console.log(error.name === 'AbortError');
   // }
   
    }
    
  },
  created(){
    this.reNew();
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.clock-border{
  width: 20rem;
  border: 0.125rem solid rgb(0, 0, 0);
  padding: 3.125rem;
  margin: 1.25rem;
  background-color:rgba(240, 255, 255, 0.082)
}
.title{
  position:relative; top: -1.5625rem;
}
.time{
  font-size:1.375rem;
  font-weight: bold;
}
</style>
