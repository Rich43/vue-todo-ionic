<template>
  <div class="home">
    <AddForm v-bind:items="todoItems" @todoSubmit="todoSubmit($event)" @todoDelete="deleteButtonClicked($event)" />
    <TodoList v-bind:items="todoItems" @checkboxClicked="checkboxClicked($event)" />
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
      todoItems: [{id: 0, value: 'test', checked: false}, {id: 1, value: 'foo', checked: false}]
    }),
    methods: {
      checkboxClicked(event: any) {
        const index = this.todoItems.findIndex(item => item.id === event.id);
        this.todoItems[index].checked = event.checked;
      },
      deleteButtonClicked(event: any) {
        this.todoItems.filter(item => item.checked).forEach(item => {
          this.todoItems.splice(this.todoItems.findIndex(todoItem => todoItem.id === item.id), 1);
        });
      },
      todoSubmit(event: any) {
        const lastTodo = this.todoItems.slice().reverse()[0];
        this.todoItems.push({id: lastTodo.id + 1, value: event, checked: false});
      }
    },
    setup() {
      return {

      }
    }
  });
</script>
