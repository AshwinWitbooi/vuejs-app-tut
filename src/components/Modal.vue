<template>
    <div class="backdrop" @click.self="closeModel">
        <div class="modal">          
          <slot></slot>
          <div class="actions">
            <slot name="links"></slot>
          </div>
        </div>
    </div>
</template>
<script>
export default {
  props:[],
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

/* Base link styles in modal */
.actions a {
  color: #1e90ff; /* Dodger Blue */
  text-decoration: none;
  font-weight: 500;
  transition: color 0.3s ease, text-decoration 0.3s ease;
  padding-right: 20px;
}

/* Hover state */
.actions a:hover {
  color: #0a75c2;
  text-decoration: underline;
}

/* Focus state for accessibility */
.actions a:focus {
  outline: 2px dashed #0a75c2;
  outline-offset: 3px;
  color: #0a75c2;
}

/* Visited state (optional) */
.actions a:visited {
  color: #6a5acd; /* Slate Blue */
}

/* Active state */
.actions a:active {
  color: #003f7d;
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