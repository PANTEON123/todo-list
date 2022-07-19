<template>
  <div class="blur"></div>
</template>

<script>
export default {
  name: "blur-background",
};
</script>

<style scoped>
.blur {
  position: absolute;
  left: 0px;
  top: 0px;
  width: 100vw;
  height: 100vh;
  background: rgba(255, 255, 255, 0.01);
  backdrop-filter: blur(4px);
}
</style>