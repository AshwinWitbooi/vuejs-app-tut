<template>
    <div>
      <h1>{{ title }}</h1>
      <div v-if="showModel">
         <Modal  :text="text" @close="toggleModel">
            <template v-slot:links>
              <a href="#">Sign up here</a>
              <a href="#">More info</a>
            </template>
            <h1>{{header}}</h1>
            <p>{{text}}</p>
         </Modal>
      </div>
      <br>
      <button class="button-light-blue" @click="toggleModel">Open Modal</button>
    </div>
</template>

<script>
import Modal from './components/Modal.vue';

export default {
  name: 'App',
  components:{ Modal },
  data() {
    return {
      title:'MY FIRST VUE JS APP',
      header:'You will be successful. Signup!',
      text:'You are winning Daily Lotto today.',
      showModel:false
    }
  },
  methods: {
    toggleModel() {
      this.showModel = !this.showModel
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
h1 {
  border-bottom: 2px solid #333; /* Dark gray line */
  padding-bottom: 0.5em;         /* Space between text and border */
  margin-bottom: 1em;            /* Space below the header */
  color: royalblue;
}

.button-light-blue {
  background-color: #4fc3f7; /* light sky blue */
  color: black;
  border: none;
  padding: 0.6rem 1.2rem;
  font-size: 1rem;
  font-weight: 600;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  border-radius: 6px;
  cursor: pointer;
  transition: background-color 0.3s ease, box-shadow 0.2s ease;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
}

.button-light-blue:hover {
  background-color: #29b6f6; /* slightly deeper blue on hover */
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.15);
}

.button-light-blue:focus {
  outline: none;
  box-shadow: 0 0 0 3px rgba(79, 195, 247, 0.4); /* focus ring */
}

.button-light-blue:active {
  background-color: #03a9f4;
  box-shadow: inset 0 2px 4px rgba(0, 0, 0, 0.15);
}

</style>
