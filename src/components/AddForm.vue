<template>
  <form class="form-horizontal" v-on:submit.prevent>
    <ion-item class="form-field">
      <ion-label position="floating">Todo text</ion-label>
      <ion-input v-model="todoText" type="text" id="todoText"></ion-input>
    </ion-item>
    <ion-item class="submit-button">
      <ion-button type="submit" @click="$emit('todoSubmit', todoText)">Add todo item</ion-button>
    </ion-item>
  </form>
  <ion-button @click="$emit('todoDelete')"><ion-icon style="color:black;" slot="icon-only" icon="trash" /></ion-button>
</template>

<script lang="ts">
import {defineComponent, PropType} from "vue";
import {TodoItems} from "@/interfaces";
import {IonButton, IonInput, IonItem, IonLabel} from "@ionic/vue";
import { addIcons } from 'ionicons';
import { trash } from 'ionicons/icons';

export default defineComponent({
  name: 'AddForm',
  data: () => ({
    todoText: ''
  }),
  components: {
    IonItem,
    IonLabel,
    IonInput,
    IonButton,
  },
  props: {
    items: Array as PropType<Array<TodoItems>>,
  },
  created() {
    addIcons({
      trash
    });
  }
});
</script>

<style lang="scss" scoped>
.base {
  display: flex;
  align-items: center;

  .form-horizontal {
    flex-direction: row;
  }

  .form-field {
    flex-direction: column;
    padding-right: 16px;
  }
}

.submit-button {
  max-height: 36px;
  margin-right: 16px;
}
</style>
