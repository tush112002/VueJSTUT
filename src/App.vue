<template>
  <HelloWorld msg="Welcome to Your Vue.js App"/>
  <ChildComponent/>
  <ChildComponent> <h1> Hi</h1></ChildComponent>
  <h1>{{name}}</h1>
  <h2 ref="count">{{ counter }}</h2>
  <button v-on:click="counter = counter + 1">Update</button>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import ChildComponent from './components/ChildComponent.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    ChildComponent
  },
  data(){
    return{
      name : "Tush",
      counter : 0
    }
  },
  beforeCreate(){
    alert("Before created")
  },
  created(){
    this.name = "Moxley"
    alert("Created");
  },
  beforeMount(){
    console.log("Before Mount", this.$el)
  },
  mounted(){
    console.log("Mounted", this.$el)
  },
  beforeUpdate(){
    console.log("before update", this.$refs['count'].textContent);
  },
  updated(){
    console.log("after update", this.$refs['count'].textContent);
  }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
