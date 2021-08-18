<template>
  <div>
    <h1>{{ msg }}</h1>
    <ion-list-header>Todo List</ion-list-header>
    <ion-list v-for="todo of items" :key="todo.id">
      <ion-item>
        <ion-label v-bind:todo="todo"></ion-label>
      </ion-item>
    </ion-list>
  </div>
</template>

<script lang="ts">
import {IonItem, IonLabel, IonList, IonListHeader} from "@ionic/vue";
  import {defineComponent} from "vue";
  export default defineComponent({
    name: 'TodoList',
    props: {
      items: [{id: Number, value: String}],
    },
    components: {
      IonList,
      IonListHeader,
      IonItem,
      IonLabel,
    },
    setup() {
      return {

      }
    }
  });
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
