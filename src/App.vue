<template>
  <div id="app">
    <Header @showModal="isVisibleModal = true" />
    <Controller />
    <Table :todos="todos" @done="done" />

    <Modal v-if="isVisibleModal" @close="isVisibleModal = false" @add="add" />
    <Blur v-if="isVisibleModal" />
  </div>
</template>

<script>
import Header from "@/components/Header";
import Controller from "@/components/Controller";
import Table from "@/components/table/Table";
import Modal from "@/components/Modal.vue";
import Blur from "@/components/Blur.vue";

export default {
  name: "App",
  components: {
    Header,
    Controller,
    Table,
    Modal,
    Blur,
  },
  data() {
    return {
      isVisibleModal: false,
      todos: [
        { name: "Что-то сделать", isDone: false },
        { name: "Еще что-то сделать", isDone: false },
      ],
    };
  },
  mounted() {
    if (localStorage.getItem("todos")) {
      this.todos = JSON.parse(localStorage.getItem("todos"));
    }
  },
  methods: {
    done(index) {
      this.todos[index].isDone = !this.todos[index].isDone;
    },
    add(description) {
      this.todos.push({
        name: description,
        isDone: false,
      });
      localStorage.setItem("todos", JSON.stringify(this.todos));
    },
  },
};
</script>

<style>
body {
  margin: 0px;
  display: flex;
  justify-content: center;
  align-items: center;
}

#app {
  width: 90vw;
  height: 60vh;
  padding-top: 100px;
  background: rgba(255, 255, 255, 0.9);
  color: #000;
  font-family: Lucida Console;
  border-radius: 0px 0px 20px 20px;
}

button:hover {
  cursor: pointer;
  transform: translateY(-2px);
}
</style>
