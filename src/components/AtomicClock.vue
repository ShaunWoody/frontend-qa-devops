<template>

<div class = "clock-border">
  
  <h1 class = "title">{{title}}</h1>

  <p class = "time">{{date}}</p>
  <p class = "time">{{time}}</p>

  
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
      date:''
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
      this.time = this.data[1]
      this.date = this.data[0]

      setTimeout(this.reNew,300)
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
  background-color:rgba(230, 108, 27, 0.082)
}
.title{
  position:relative; top: -1.2rem;
  
}
.time{
  font-size:1.375rem;
  font-weight: bold;
}
</style>
