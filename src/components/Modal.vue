<template>
    <div class="backdrop">
        <div class="modal">
            <p>Modal content here</p>
        </div>
    </div>
</template>

<style>
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


</style>