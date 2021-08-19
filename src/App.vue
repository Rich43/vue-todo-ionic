<template>
  <IonApp>
    <Home />
  </IonApp>
</template>

<script lang="ts">
import {IonApp,} from '@ionic/vue';
import {defineComponent} from 'vue';
import Home from "@/views/Home.vue";

export default defineComponent({
  name: 'App',
  components: {
    IonApp,
    Home,

  },
  setup() {
    return {

    }
  }
});
</script>

<style scoped>

</style>
