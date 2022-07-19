<template>
  <div class="modal">
    <div class="header">
      <div class="title">Создать новую задачу</div>
      <img class="img" src="@/assets/close.svg" @click="close" />
    </div>
    <div class="body">
      <div class="subtitle">Описание</div>
      <input type="text" v-model="description" />
    </div>
    <button @click="add">Создать</button>
  </div>
</template>

<script>
export default {
  name: "modal-window",
  data() {
    return {
      description: "",
    };
  },
  methods: {
    close() {
      this.description = "";
      this.$emit("close");
    },
    add() {
      this.$emit("add", this.description);
      this.close();
    },
  },
};
</script>

<style scoped>
.modal {
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  display: flex;
  flex-direction: column;
  width: 400px;
  padding: 40px 40px 50px;
  background: #fff;
  border: 1px solid #dde2e4;
  box-shadow: 0px 25px 50px -12px rgba(0, 0, 0, 0.25);
  border-radius: 6px;
  z-index: 100;
}

.header {
  display: flex;
  justify-content: space-between;
  margin-bottom: 30px;
}

.title {
  font-weight: 700;
  font-size: 18px;
  line-height: 132%;
  color: #16191d;
}

.subtitle {
  margin-bottom: 5px;
}

.body {
  margin-bottom: 30px;
}

input {
  min-width: 100%;
  padding: 5px;
  border: 1px solid #dde2e4;
  border-radius: 8px;
  outline: none;
  opacity: 0.5;
  box-sizing: border-box;
}

button {
  padding: 12px 0px;
  background: #f0f5ff;
  border-radius: 8px;
  border: 0px;
  outline: none;
}

.img:hover {
  cursor: pointer;
}
</style>