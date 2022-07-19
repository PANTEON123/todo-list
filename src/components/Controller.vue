<template>
  <div class="controller">
    <img class="glass" src="../assets/Vector.svg" />
    <input type="text" placeholder="Поиск ID, Имени, статуса или даты" />

    <span class="sorting">Сортировать по:</span>
    <span class="filter"
      >Дата <img class="arrow" src="../assets/Vector 9.svg"
    /></span>
  </div>
</template>

<script>
export default {
  name: "input-controller",
};
</script>

<style scoped>
.controller {
  display: flex;
  align-items: center;
  padding-left: 40px;
}

.sorting {
  margin-right: 15px;
  margin-left: auto;
}

.glass {
  margin-right: 16px;
  width: 18px;
  height: 18px;
}

input {
  width: 227px;
  height: 18px;
  border: 0px;
  outline: none;
}

.arrow {
  width: 6px;
  height: 12px;
}

.filter:hover {
  cursor: pointer;
}
</style>