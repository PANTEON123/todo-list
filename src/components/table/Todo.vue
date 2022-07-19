<template>
  <li class="todo">
    <span class="img" @click="$emit('done', index)">
      <img v-if="!todo.isDone" src="../../assets/Ellipse 35.svg" />
      <img v-else src="../../assets/Group 1427.svg" />
    </span>
    <span class="name">{{ todo.name }} </span>
    <span :class="{ statusActive: todo.isDone, status: !todo.isDone }">
      <template v-if="todo.isDone">Выполнено</template>
      <template v-else>Не выполнено</template>
    </span>
    <span class="date">15.03.22</span>
  </li>
</template>

<script>
export default {
  name: "todo-of-list",
  props: ["todo", "index"],
};
</script>

<style scoped>
.todo {
  display: grid;
  grid-template-columns: 80px 70vw 120px auto;
  padding: 20px 0px;
  font-family: "Vela Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 132%;
  border-bottom: 1px solid #eeebe9;
}

.todo:first-child {
  border-top: 1px solid #eeebe9;
}

.img {
  text-align: center;
}

.img:hover {
  cursor: pointer;
}

.name {
}

.status {
  color: #f89b11;
}

.statusActive {
  color: #134ec1;
}

.date {
}

img {
  width: 20px;
}
</style>