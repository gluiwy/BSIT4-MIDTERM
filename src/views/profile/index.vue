<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-Title> Profile Screen </ion-Title>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true">
      <h1 class="px-4 py-3">User</h1>

      <div class="px-5">
        <h6>Name: Tahanlangit, Louie A.</h6>
        <h6>Course: BSIT-4</h6>
        <h6>E-mail Address: .... </h6>
      </div>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import {
  IonToolbar,
  IonTitle,
  IonHeader,
  IonPage,
  IonContent,
  IonFooter,
} from '@ionic/vue';

export default defineComponent({
  name: 'SignInScreen',
  components: {
    IonToolbar,
    IonTitle,
    IonHeader,
    IonPage,
    IonContent,
    IonFooter,
  },
});
</script>
