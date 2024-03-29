<template>
<h1>{{count}}</h1>
<button v-on:click="count= count + 1">+</button>
<button v-on:click="count= count - 1">-</button>
</template>

<script>
export default {
  name: 'HelloWorld',
  data(){
    return{
      count : 0
    }
  },
  watch:{
    count(val,prev){
      if(val>5 && val>prev){
        this.count = 0
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
