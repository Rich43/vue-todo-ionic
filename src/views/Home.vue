<template>
  <div class="home">
    <AddForm v-bind:items="todoItems" @todoSubmit="todoItems.push({id: todoItems.slice().reverse()[0].id + 1, value: $event})" />
    <TodoList v-bind:items="todoItems" />
  </div>
</template>

<script lang="ts">
  import TodoList from '@/components/TodoList.vue';
  import {defineComponent} from "vue";
  import AddForm from "@/components/AddForm.vue";

  export default defineComponent({
    name: 'Home',
    components: {
      AddForm,
      TodoList
    },
    data: () => ({
      todoItems: [{id: 0, value: 'test'}, {id: 1, value: 'foo'}]
    }),
    setup() {
      return {

      }
    }
  });
</script>
