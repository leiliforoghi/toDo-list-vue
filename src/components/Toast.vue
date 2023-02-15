<template>
  <div class="toast-wrapper">
    <div class="toast">
      You Must Enter a Value For The Todo
    </div>
  </div>
</template>

<style>
.toast-wrapper {
  position: fixed;
  width: 100%;
  top: 20px;
}

.toast {
  padding: 20px;
  color: white;
  background: #d8437c;
  border-radius: 10px;
  box-shadow: 1px 3px 5px rgba(209, 204, 204, 0.2);
  max-width: 400px;
  margin: 0 auto;
}
</style>