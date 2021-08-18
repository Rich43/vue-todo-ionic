<template>
  <div>
    <h1>{{ msg }}</h1>
    <ion-list-header>Todo List</ion-list-header>
    <ion-list v-for="todo of items" :key="todo.id">
      <ion-item>
        <ion-label>{{ todo.value }}</ion-label>
        <ion-checkbox slot="start"></ion-checkbox>
      </ion-item>
    </ion-list>
  </div>
</template>

<script lang="ts">
import {IonCheckbox, IonItem, IonLabel, IonList, IonListHeader} from "@ionic/vue";
import {defineComponent, PropType} from "vue";
import {TodoItems} from "@/interfaces";

export default defineComponent({
  name: 'TodoList',
  props: {
    items: Array as PropType<Array<TodoItems>>,
  },
  components: {
    IonList,
    IonListHeader,
    IonItem,
    IonLabel,
    IonCheckbox
  },
  setup() {
    return {}
  }
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
