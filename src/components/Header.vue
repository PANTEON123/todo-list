<template>
  <div class="header">
    <div class="title">To do list</div>
    <img
      src="../assets/Component 36.svg"
      @click="$emit('showModal')"
      class="button"
    />
  </div>
</template>

<script>
export default {
  name: "app-header",
};
</script>

<style scoped>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 30px;
}

.title {
  padding-left: 40px;
  font-family: "Montserrat";
  font-weight: 700;
  font-size: 24px;
  line-height: 132%;
  color: #16191d;
}

.button {
  width: 40px;
  height: 40px;
  background: none;
  border: 0px;
  border-radius: 100%;
}

.button:hover {
  transform: translateY(-2px);
  cursor: pointer;
}
</style>
