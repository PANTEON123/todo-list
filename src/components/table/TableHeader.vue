<template>
  <div class="table-header">
    <span></span>
    <span class="description">Описание</span>
    <span class="status">Статус</span>
    <span class="date">Дата</span>
  </div>
</template>

<script>
export default {
  name: "table-header",
};
</script>

<style scoped>
.table-header {
  display: grid;
  grid-template-columns: 100px 70vw 120px auto;
  align-items: center;
  margin-top: 30px;
  font-family: "Vela Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 132%;
  height: 32px;
}

.description {
  border-left: 1px solid black;
  padding-left: 20px;
}

.status {
  border-left: 1px solid black;
  padding-left: 20px;
}

.date {
  border-left: 1px solid black;
  padding-left: 20px;
}
</style>