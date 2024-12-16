<template>
  <ion-page>
    <ion-header>
      <ion-toolbar color="warning">
        <ion-buttons slot="start">
          <ion-back-button></ion-back-button>
        </ion-buttons>
        <ion-title> GPS | Geolocation </ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content>
      <div class="p-3">
        <button class="btn btn-primary btn-lg w-100" @click="getGeo()">
          Get Geolocation
        </button>

        <div class="mt-4">
          <p>Latitute</p>
          <input v-model="coords.latitude" type="text" class="form-control" />
        </div>
        <div class="mt-4">
          <p>Longitude</p>
          <input v-model="coords.longitude" type="text" class="form-control" />
        </div>
      </div>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { menu, home, person } from 'ionicons/icons';
import { Geolocation } from '@capacitor/geolocation';

import {
  IonBackButton,
  IonButtons,
  IonToolbar,
  IonTitle,
  IonHeader,
  IonPage,
  IonContent,
  IonIcon,
  IonRouterOutlet,
} from '@ionic/vue';

export default defineComponent({
  name: 'GPSScreen',
  components: {
    IonBackButton,
    IonButtons,
    IonToolbar,
    IonTitle,
    IonHeader,
    IonPage,
    IonContent,
    IonIcon,
    IonRouterOutlet,
  },
  data() {
    return {
      coords: {} as any,
    };
  },
  methods: {
    async getGeo() {
      const coordinates = await Geolocation.getCurrentPosition();
      this.coords = coordinates.coords;
    },
  },
  setup() {
    return {
      menu,
      home,
      person,
    };
  },
});
</script>
