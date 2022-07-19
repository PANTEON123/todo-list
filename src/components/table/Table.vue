<template>
  <div class="table">
    <TableHeader />
    <ul class="list">
      <Todo
        v-for="(todo, index) in todos"
        :key="'i-' + index"
        :todo="todo"
        :index="index"
        @done="done"
      />
    </ul>
  </div>
</template>

<script>
import TableHeader from "@/components/table/TableHeader";
import Todo from "@/components/table/Todo";

export default {
  name: "todo-list",
  props: ["todos"],
  components: {
    TableHeader,
    Todo,
  },
  methods: {
    done(index) {
      this.$emit("done", index);
    },
  },
};
</script>

<style scoped>
</style>