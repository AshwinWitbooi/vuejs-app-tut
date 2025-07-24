<template>
    <div>
      <h1>{{ title }}</h1>
      <Modal/>
    </div>
</template>

<script>
import Modal from './components/Modal.vue';

export default {
  name: 'App',
  components:{ Modal },
  data() {
    return {
      title:'MY FIRST VUE JS APP'
    }
  },
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
h1 {
  border-bottom: 2px solid #333; /* Dark gray line */
  padding-bottom: 0.5em;         /* Space between text and border */
  margin-bottom: 1em;            /* Space below the header */
  color: royalblue;
}

</style>
