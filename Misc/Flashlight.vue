<!--
    Credits: Pranev (aka) NeTT
    Github: https://github.com/retraigo
    Discord: https://discord.gg/A69vvdK
-->
<template>
  <div>
    <div class="top-container">
      <div
        class="main-content"
        @mousemove="movedaro"
      >
        <div
          class="movingPointer"
          ref="movingthing"
          :style="{
            left: coordinates.x + 'px',
            top: coordinates.y - 40 + 'px',
          }"
        />
      </div>
    </div>
  </div>
</template>
<style scoped>
.movingPointer {
    background-image: url(/cover-no-text.png);
    background-position: center;
    background-size: cover;
    background-attachment: fixed;
    position: absolute;
    width: 30rem;
    height: 30rem;
    filter: blur(16px);
    border-radius: 9999px;
    background-color: white;
    z-index: 40;
    opacity: 50;
}
.top-container {
    min-height: 100vh;
    background-color: #1d001600;
    position: relative;
    overflow: hidden;
    cursor: none;
}
.main-content {
    min-height: 100vh;
    position: absolute;
    background-color: black;
    z-index: 30;
    left: 0;
    top: 0;
    right: 0;
    bottom: 0;
    width: 100%;
}
</style>
<script setup lang="ts">
const coordinates = ref<{x: number, y: number}>({ x: 0, y: 0 });
function movedaro(e) {
  coordinates.value.x = e.pageX - 100;
  coordinates.value.y = e.pageY;
}
</script>
