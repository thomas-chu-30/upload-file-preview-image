<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Hello Vue 3 + Vite" /> -->
  <form>
    <input @change="getFile($event)" type="file" id='upload_file'/>
    <p>{{url}}</p>
    <img v-if='url' :src="url" />
  </form>
  
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import {ref} from 'vue'
export default {
  setup(){
    let url = ref('')
    const getFile = ($event)=> {

      const file = $event.target.files[0]

      url.value = URL.createObjectURL(file);
    
    }
    return {getFile,url}
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