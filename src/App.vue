<template>
  <div id="app">
    <Header />
    <Todos v-bind:todos="todos" />
     <WeatherInfo />
  </div>

</template>

<script>
import Header from "./components/layout/Header";
import Todos from './components/Todos';
import WeatherInfo from './components/WeatherInfo';

export default {
  name: 'app',
  components: {
    Header,
    Todos,
    WeatherInfo
  },
  data(){
    return {
      todos: [
        {
          id: 1,
          title: "Item one",
          completed: false
        },
        {
          id: 2,
          title: "Item two",
          completed: true
        },
        {
          id: 3,
          title: "Item three",
          completed: true
        }
      ]
    }
  }
}
</script>

<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  body {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }
</style>
