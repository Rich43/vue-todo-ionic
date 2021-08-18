<template>
  <div class="home">
    <TodoList v-bind:items="items" />
  </div>
</template>

<script lang="ts">
  import { Options, Vue } from 'vue-class-component';
  import TodoList from '@/components/TodoList.vue';

  @Options({
    data: {
      items: [{id: 0, value: 'test'}, {id: 1, value: 'foo'}]
    },
    components: {
      TodoList,
    },
  })
  export default class Home extends Vue {}
</script>
