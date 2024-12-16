<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-buttons slot="start">
          <ion-back-button></ion-back-button>
        </ion-buttons>
        <ion-Title> Index Page </ion-Title>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true">
      <h1 class="px-4 py-5 text-center">This is the Index Page</h1>
    </ion-content>

    <ion-footer>
      <ion-toolbar class="p-1">
        <button slot="end" class="btn btn-primary w-25" @click="nextScreen()">
          Home
        </button>
      </ion-toolbar>
    </ion-footer>
  </ion-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import {
  IonBackButton,
  IonButtons,
  IonToolbar,
  IonTitle,
  IonHeader,
  IonPage,
  IonContent,
  IonFooter,
} from '@ionic/vue';

export default defineComponent({
  name: 'IndexScreen',
  components: {
    IonBackButton,
    IonButtons,
    IonToolbar,
    IonTitle,
    IonHeader,
    IonPage,
    IonContent,
    IonFooter,
  },
  methods: {
    async nextScreen() {
      this.$router.push('./tabs/home');
    },
  },
});
</script>
