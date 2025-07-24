<template>
    <div class="backdrop" @click="closeModel">
        <div class="modal">
             <h1>{{header}}</h1>
            <p>{{text}}</p>
        </div>
    </div>
</template>
<script>
export default {
  props:[
    'header',
    'text'
  ],
   methods:{
    closeModel(){
      this.$emit('close')
    }
  }
}
</script>
<style scoped>
.backdrop {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;

  background-color: rgba(0, 0, 0, 0.5); /* Semi-transparent black */
  backdrop-filter: blur(2px);          /* Optional: subtle blur effect */

  z-index: 999;                         /* High z-index to appear above content */
}

.modal {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);

  background-color: #fff;
  padding: 2rem;
  border-radius: 8px;
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);

  z-index: 1000; /* Higher than backdrop */
  width: 90%;
  max-width: 500px;

  animation: slideFadeIn 0.3s ease;
}

h1 {
color:purple; /* deep green */
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  font-size: 1.5rem;
  font-weight: 700;
  margin: 0;
  text-shadow: 1px 1px 2px rgba(46, 125, 50, 0.2); /* soft shadow for depth */
  letter-spacing: 0.5px;
}
</style>