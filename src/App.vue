
<template>

  <div id="app">
 <h3> {{title}}</h3>
 <div class='col-md-12'>
  <Character 
    v-for='(id,index) in initial_ids'
    :id ='id'
     :key='index'
   />
  </div>
  </div>
</template>

<script>
import Character from './components/Character.vue'

export default {
  name: 'app',
  data(){
    return{
      title:
      'Generate Your Team',
       initial_ids:[1,3,4]
    }
 }, 
 components:{
 Character
 }
}
  

</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: whitesmoke;
  background-color: #2c3e50;
  margin-top:60px;
}
body{
  background-color: #2c3e50;
}

.character-card{
  border:2px solid #4fc08d;
  border-radius: 4px;
  cursor:pointer;

}
</style>

