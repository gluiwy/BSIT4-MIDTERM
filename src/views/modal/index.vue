<template>
  <ion-page>
    <ion-header>
      <ion-toolbar color="warning">
        <ion-buttons slot="start">
          <ion-back-button></ion-back-button>
        </ion-buttons>
        <ion-title>Modal</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true" class="ion-padding">
      <ion-button expand="block" @click="openModal">Open</ion-button>
      <p>{{ message }}</p>
    </ion-content>

    <ion-footer>
      <ion-toolbar class="p-1">
        <ion-tabs>
          <ion-router-outlet></ion-router-outlet>
          <ion-tab-bar slot="bottom">
            <ion-tab-button tab="tab1" href="/tabs/home">
              <ion-icon aria-hidden="true" :icon="home" />
              <ion-label>Home</ion-label>
            </ion-tab-button>

            <ion-tab-button tab="tab2" href="/tabs/profile">
              <ion-icon aria-hidden="true" :icon="person" />
              <ion-label>Profile</ion-label>
            </ion-tab-button>

            <ion-tab-button tab="tab3" href="/tabs/menu">
              <ion-icon aria-hidden="true" :icon="menu" />
              <ion-label>Menu</ion-label>
            </ion-tab-button>
          </ion-tab-bar>
        </ion-tabs>
      </ion-toolbar>
    </ion-footer>
  </ion-page>
</template>

<script lang="ts">
import {
  IonButton,
  IonContent,
  IonPage,
  IonHeader,
  IonToolbar,
  IonTitle,
  modalController,
} from '@ionic/vue';

import Modal from '@/views/modal/modal.vue';
import { ref, defineComponent } from 'vue';
import { IonBackButton, IonButtons, IonRouterOutlet } from '@ionic/vue';
import { menu, home, person } from 'ionicons/icons';

export default defineComponent({
  name: 'modalPage',
  components: {
    IonButton,
    IonBackButton,
    IonContent,
    IonPage,
    IonHeader,
    IonToolbar,
    IonTitle,
    IonRouterOutlet,
  },
  setup() {
    const message = ref(
      'This modal example uses the modalController to present and dismiss modals.'
    );

    const openModal = async () => {
      const modal = await modalController.create({
        component: Modal,
      });

      await modal.present();

      const { data, role } = await modal.onWillDismiss();

      if (role === 'confirm') {
        message.value = `Hello, ${data}!`;
      }
    };

    return {
      message,
      openModal,
      menu,
      home,
      person,
    };
  },
});
</script>
