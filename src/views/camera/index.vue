<template>
  <ion-page>
    <ion-header>
      <ion-toolbar color="warning">
        <ion-buttons slot="start">
          <ion-back-button></ion-back-button>
        </ion-buttons>
        <ion-title> Camera </ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content>
      <div class="p-3">
        <button class="btn btn-primary btn-lg w-100" @click="takePhoto()">
          Take a Photo
        </button>
      </div>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { menu, home, person } from 'ionicons/icons';
import { Camera, CameraResultType } from '@capacitor/camera';

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
  name: 'cameraScreen',
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
    return {};
  },
  methods: {
    async takePhoto() {
      const image = await Camera.getPhoto({
        quality: 4000,
        allowEditing: true,
        resultType: CameraResultType.Uri,
      });
      var imageUrl = image.webPath;
      //imageElement.src = imageUrl;
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
