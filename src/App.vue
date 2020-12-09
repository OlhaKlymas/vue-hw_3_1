<template>
  <div id="app">
    <Select :value.sync="customSelect" :selectOption="selectOption"/>
  </div>
</template>

<script>
import Select from './components/Select'
export default {
  name: 'App',
  components: {
    Select
  },
  data(){
    return{
      selectOption: {
        male: 'мужской',
        female: 'женский',
        other: 'другой'
      },
      customSelect: ''
    }
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
